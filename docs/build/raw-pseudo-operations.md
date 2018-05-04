---
title: 원시 의사 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff3b9dd065b4bf1f64950f97237dec08b10d23cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="raw-pseudo-operations"></a>원시 의사 작업
이 항목에서는 의사 작업을 나열 합니다.  
  
## <a name="remarks"></a>설명  
  
|의사 작업|설명|  
|----------------------|-----------------|  
|PROC 프레임 [: ehandler]|함수를 생성 하는 MASM.pdata에 항목 테이블 원인과 함수의 구조적에 대 한.xdata에서 정보를 해제 예외 처리 동작을 해제 합니다.  Ehandler가 있는 경우이 프로시저는 언어별 처리기로.xdata에 입력 됩니다.<br /><br /> 프레임 특성을 사용 하는 경우 뒤에 야 하 여 프로그램. 프롤로그 끝 지시문입니다.  리프 함수인 경우 함수 (에 정의 된 대로 [함수 형식](../build/function-types.md)) 프레임 특성은 이러한 의사 (pseudo)이 작업의 나머지 부분에는 필요 하지 않습니다.|  
|. PUSHREG reg|현재는 프롤로그의 오프셋을 사용 하 여 지정 된 레지스터 번호에 대 한 UWOP_PUSH_NONVOL 해제 코드 항목을 생성 합니다.<br /><br /> 정수 비휘발성 레지스터와만 사용 해야 합니다.  휘발성 레지스터의 푸시를 사용 하 여 프로그램. ALLOCSTACK 8 대신|  
|. SETFRAME reg, 오프셋|프레임에서 채우기 해제 정보의 지정 된 레지스터와 오프셋을 사용 하 여 필드와 오프셋을 등록 합니다. 오프셋은 16의 배수 여야 합니다. 및 240 합니다. 또한이 지시문은 현재 프롤로그 오프셋을 사용 하 여 지정된 된 레지스터의 uwop_set_fpreg 해제 코드를 생성 합니다.|  
|. ALLOCSTACK 크기|UWOP_ALLOC_SMALL 또는 현재 오프셋에 대 한 지정 된 크기가 UWOP_ALLOC_LARGE 프롤로그에 생성 됩니다.<br /><br /> 크기 피연산자 8의 배수 여야 합니다.|  
|. SAVEREG reg, 오프셋|UWOP_SAVE_NONVOL 또는 지정 된 레지스터와 현재 프롤로그 오프셋을 사용 하 여 오프셋에 대 한 UWOP_SAVE_NONVOL_FAR 해제 코드 항목 중 하나를 생성 합니다. MASM 가장 효율적인 인코딩 선택 합니다.<br /><br /> 오프셋은 양수, 및 8의 배수 여야 합니다.  오프셋은 rsp 구성에는 일반적으로 프로시저의 프레임을 로그의 기준으로 또는 프레임 포인터, 소수 자릿수가 없는 프레임 포인터를 사용 합니다.|  
|. SAVEXMM128 reg, 오프셋|UWOP_SAVE_XMM128 또는 지정 된 XMM 레지스터와 현재 프롤로그 오프셋을 사용 하 여 오프셋에 대 한 UWOP_SAVE_XMM128_FAR 해제 코드 항목 중 하나를 생성 합니다. MASM 가장 효율적인 인코딩 선택 합니다.<br /><br /> 오프셋은 양수, 및 16의 배수 여야 합니다.  오프셋은 rsp 구성에는 일반적으로 프로시저의 프레임을 로그의 기준으로 또는 프레임 포인터, 소수 자릿수가 없는 프레임 포인터를 사용 합니다.|  
|. PUSHFRAME [code]|UWOP_PUSH_MACHFRAME 해제 코드 항목을 생성합니다. 선택 사항인 코드를 지정 하는 경우 해제 코드 항목 1의 한정자를 제공 됩니다. 그렇지 않으면 한정자는 0입니다.|  
|.ENDPROLOG|프롤로그 선언의 끝 신호를 보냅니다.  함수의 첫 번째 255 바이트에서 수행 되어야 합니다.|  
  
 대부분의 opcode 적절 한 사용 하 여 샘플 함수 프롤로그는 다음과 같습니다.  
  
```  
sample PROC FRAME     
   db      048h; emit a REX prefix, to enable hot-patching  
push rbp  
.pushreg rbp  
sub rsp, 040h  
.allocstack 040h     
lea rbp, [rsp+020h]  
.setframe rbp, 020h  
movdqa [rbp], xmm7  
.savexmm128 xmm7, 020h;the offset is from the base of the frame  
;not the scaled offset of the frame  
mov [rbp+018h], rsi  
.savereg rsi, 038h  
mov [rsp+010h], rdi  
.savereg rdi, 010h; you can still use RSP as the base of the frame  
; or any other register you choose  
.endprolog  
  
; you can modify the stack pointer outside of the prologue (similar to alloca)  
; because we have a frame pointer.  
; if we didn’t have a frame pointer, this would be illegal  
; if we didn’t make this modification,  
; there would be no need for a frame pointer  
  
sub rsp, 060h  
  
; we can unwind from the following AV because of the frame pointer  
  
mov rax, 0  
mov rax, [rax] ; AV!  
  
; restore the registers that weren’t saved with a push  
; this isn’t part of the official epilog, as described in section 2.5  
  
movdqa xmm7, [rbp]  
mov rsi, [rbp+018h]  
mov rdi, [rbp-010h]  
  
; Here’s the official epilog  
  
lea rsp, [rbp-020h]  
pop rbp  
ret  
sample ENDP  
```  
  
## <a name="see-also"></a>참고 항목  
 [MASM에 대한 해제 도우미](../build/unwind-helpers-for-masm.md)