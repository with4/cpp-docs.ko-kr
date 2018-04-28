---
title: . SETFRAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SETFRAME
dev_langs:
- C++
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c49d512534a11f01376deac41006e55c6b7b9d89
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="setframe"></a>.SETFRAME
채우기 프레임에서 레지스터에 지정된 된 레지스터를 사용 하 여 해제 정보 필드와 오프셋 (`reg`) 및 오프셋 (`offset`). 오프셋은 16의 배수 여야 합니다. 및 240 합니다. 이 지시문도 생성 한 `UWOP_SET_FPREG` 현재 프롤로그 오프셋을 사용 하 여 지정 된 등록에 대 한 코드 항목을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
.SETFRAME reg, offset  
```  
  
## <a name="remarks"></a>설명  
 . SETFRAME를 사용 하면 ml64.exe 프레임 함수, 해제 및에서 확장 되는 프롤로그만 사용할 수 방법을 지정할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 및 `.pdata`합니다. . SETFRAME 실제로 해제 해제 되도록 작업을 구현 하는 지침 뒤에 야 합니다. 해제 지시문와 실제 매크로에서 해제 하는 코드를 래핑하는 것이 좋습니다.  
  
 자세한 내용은 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
## <a name="sample"></a>샘플  
  
### <a name="description"></a>설명  
 다음 샘플에는 프레임 포인터를 사용 하는 방법을 보여 줍니다.  
  
### <a name="code"></a>코드  
  
```  
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
frmex2 PROC FRAME  
   push rbp  
.pushreg rbp  
   sub rsp, 010h  
.allocstack 010h  
   mov rbp, rsp  
.setframe rbp, 0  
.endprolog  
   ; modify the stack pointer outside of the prologue (similar to alloca)  
   sub rsp, 060h  
  
   ; we can unwind from the following AV because of the frame pointer     
   mov rax, 0  
   mov rax, [rax] ; AV!  
  
   add rsp, 060h  
   add rsp, 010h  
   pop rbp  
   ret  
frmex2 ENDP  
_text ENDS  
END  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)