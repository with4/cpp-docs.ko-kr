---
title: ".SETFRAME | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".SETFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SETFRAME directive"
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SETFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

칠 프레임에 지정한 레지스터를 사용 하 여 해제 정보의 레지스터 필드와 오프셋 \(`reg`\) 및 오프셋 \(`offset`\).  오프셋은 16의 배수여야 하고 240보다 작거나 같아야 합니다.  이 지시문에도 생성 한 `UWOP_SET_FPREG` 은 현재 프롤로그 오프셋을 사용 하 여 지정 된 레지스터에 대 한 코드 항목을 해제 합니다.  
  
## 구문  
  
```  
.SETFRAME reg, offset  
```  
  
## 설명  
 .SETFRAME ml64.exe 사용자 프레임 함수 해제를 하 고 프롤로그에서 확장에 사용할 수 있습니다 방법을 지정할 수 있습니다에서 [PROC](../../assembler/masm/proc.md) 프레임 선언에는 [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다.  이러한 지시문 코드를 생성 하지 않습니다. 생성만 `.xdata` 및 `.pdata`.  .해제 되지 않도록 하는 작업을 실제로 구현 지침에 SETFRAME가 있어야 합니다.  해제 지시문과 계약을 확인 하려면 매크로 해제 합니다 의미입니다 코드를 래핑하는 것이 좋습니다.  
  
 자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)를 참조하십시오.  
  
## 샘플  
  
### 설명  
 다음 샘플 프레임 포인터를 사용 하는 방법을 보여 줍니다.  
  
### 코드  
  
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
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)