---
title: "원시 의사 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 원시 의사 작업
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 의사 작업에 대해 설명합니다.  
  
## 설명  
  
|의사 작업|설명|  
|-----------|--------|  
|PROC FRAME \[:ehandler\]|MASM으로 .pdata에서 함수 테이블 엔트리를 생성하고 함수의 구조적 예외 처리 해제 동작을 위해 .xdata에서 정보를 해제합니다.  ehandler가 있으면 이 프로시저가 언어별 처리기로 .xdata에 입력됩니다.<br /><br /> FRAME 특성을 사용할 때는 이 특성 뒤에 .ENDPROLOG 지시문을 함께 사용해야 합니다.  함수가 리프 함수\([함수 형식](../build/function-types.md) 참조\)이면 FRAME 특성이 필요 없습니다. 이는 다른 의사 작업의 경우에도 마찬가지입니다.|  
|.PUSHREG reg|프롤로그의 현재 오프셋을 사용하여 지정된 레지스터 번호에 대한 UWOP\_PUSH\_NONVOL 해제 코드 엔트리를 생성합니다.<br /><br /> 이는 비volatile 정수 레지스터와 함께 사용해야 합니다.  volatile 레지스터를 푸시하려면 .ALLOCSTACK 8을 대신 사용해야 합니다.|  
|.SETFRAME reg, offset|지정된 레지스터와 오프셋을 사용하여 해제 정보의 프레임 레지스터 필드와 오프셋을 입력합니다.  오프셋은 16의 배수여야 하고 240보다 작거나 같아야 합니다.  이 지시문은 현재 프롤로그 오프셋을 사용하여 지정된 레지스터에 대한 UWOP\_SET\_FPREG 해제 코드 항목도 생성합니다.|  
|.ALLOCSTACK size|프롤로그의 현재 오프셋에 대해 지정된 크기를 사용하여 UWOP\_ALLOC\_SMALL 또는 UWOP\_ALLOC\_LARGE를 생성합니다.<br /><br /> size 피연산자는 8의 배수여야 합니다.|  
|.SAVEREG reg, offset|현재 프롤로그 오프셋을 사용하여 지정된 레지스터 및 오프셋에 대해 UWOP\_SAVE\_NONVOL 또는 UWOP\_SAVE\_NONVOL\_FAR 해제 코드 엔트리를 생성합니다.  MASM은 가장 효율적인 인코딩을 선택합니다.<br /><br /> 오프셋은 8의 배수인 양수여야 합니다.  오프셋은 프로시저의 프레임을 기준으로 합니다. 이 프레임은 일반적으로 RSP에 있거나 프레임 포인터를 사용하는 경우 배율 조정되지 않은 프레임 포인터입니다.|  
|.SAVEXMM128 reg, offset|현재 프롤로그 오프셋을 사용하여 지정된 XMM 레지스터 및 오프셋에 대해 UWOP\_SAVE\_XMM128 또는 UWOP\_SAVE\_XMM128\_FAR 해제 코드 엔트리를 생성합니다.  MASM은 가장 효율적인 인코딩을 선택합니다.<br /><br /> 오프셋은 16의 배수인 양수여야 합니다.  오프셋은 프로시저의 프레임을 기준으로 합니다. 이 프레임은 일반적으로 RSP에 있거나 프레임 포인터를 사용하는 경우 배율 조정되지 않은 프레임 포인터입니다.|  
|.PUSHFRAME \[code\]|UWOP\_PUSH\_MACHFRAME 해제 코드 엔트리를 생성합니다.  선택 사항인 코드를 지정한 경우 해제 코드 항목에는 한정자로 1이 지정되고,  그렇지 않으면 한정자로 0이 지정됩니다.|  
|.ENDPROLOG|프롤로그 선언의 끝을 나타내며,  함수의 처음 255바이트 내에 있어야 합니다.|  
  
 다음은 대부분의 opcode를 적절하게 사용한 함수 프롤로그 샘플입니다.  
  
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
  
## 참고 항목  
 [MASM에 대한 해제 도우미](../build/unwind-helpers-for-masm.md)