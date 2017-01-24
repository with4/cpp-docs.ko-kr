---
title: ".ALLOCSTACK | Microsoft Docs"
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
  - ".ALLOCSTACK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ALLOCSTACK directive"
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .ALLOCSTACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성 하는  **UWOP\_ALLOC\_SMALL** 또는  **UWOP\_ALLOC\_LARGE** 프롤로그의 현재 오프셋 크기를 지정 합니다.  
  
## 구문  
  
```  
.ALLOCSTACK size  
```  
  
## 설명  
 Masm에서는 지정 된 크기에 대 한 가장 효율적인 인코딩을 선택 합니다.  
  
 .ALLOCSTACK ml64.exe 사용자가 지정 하는 방법 프레임 기능을 해제 하 고 프롤로그에서 확장에 사용할 수 있습니다에서  [PROC](../../assembler/masm/proc.md) 프레임 선언에는  [.프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다.  이러한 지시문 코드를 생성 하지 않습니다. 생성만 `.xdata` 및 `.pdata`.  .해제 되지 않도록 하는 작업을 실제로 구현 지침에 ALLOCSTACK가 있어야 합니다.  해제 지시문과 계약을 확인 하려면 매크로 해제 합니다 의미입니다 코드를 래핑하는 것이 좋습니다.  
  
 `size` 피연산자는 8의 배수 여야 합니다.  
  
 자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)를 참조하십시오.  
  
## 샘플  
 다음 샘플 해제\/예외 처리기를 지정 하는 방법을 보여 줍니다.  
  
```  
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console  
text SEGMENT  
PUBLIC Example3  
PUBLIC Example3_UW  
Example3_UW PROC NEAR  
   ; exception/unwind handler body  
  
   ret 0  
  
Example3_UW ENDP  
  
Example3 PROC FRAME : Example3_UW  
  
   sub rsp, 16  
.allocstack 16  
  
.endprolog  
  
   ; function body  
    add rsp, 16  
   ret 0  
  
Example3 ENDP  
text ENDS  
END  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)