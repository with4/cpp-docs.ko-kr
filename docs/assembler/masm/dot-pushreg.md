---
title: ".PUSHREG | Microsoft Docs"
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
  - ".PUSHREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHREG directive"
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성 하는 `UWOP_PUSH_NONVOL` 현재 프롤로그에서 오프셋을 사용 하 여 숫자의 지정 된 등록에 대 한 코드 항목을 해제 합니다.  
  
## 구문  
  
```  
.PUSHREG register  
```  
  
## 설명  
 .PUSHREG ml64.exe 사용자 프레임 함수 해제를 하 고 프롤로그에서 확장에 사용할 수 있습니다 방법을 지정할 수 있습니다에서 [PROC](../../assembler/masm/proc.md) 프레임 선언에는 [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다.  이러한 지시문 코드를 생성 하지 않습니다. 생성만 `.xdata` 및 `.pdata`.  .해제 되지 않도록 하는 작업을 실제로 구현 지침에 PUSHREG가 있어야 합니다.  해제 지시문과 계약을 확인 하려면 매크로 해제 합니다 의미입니다 코드를 래핑하는 것이 좋습니다.  
  
 자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)를 참조하십시오.  
  
## 샘플  
  
### 설명  
 다음 샘플 비휘발성 tegisters 밀기 방법을 보여 줍니다.  
  
### 코드  
  
```  
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
Example1 PROC FRAME  
   push r10  
.pushreg r10  
   push r15  
.pushreg r15  
   push rbx  
.pushreg rbx  
   push rsi  
.pushreg rsi  
.endprolog  
   ; rest of function ...  
   ret  
Example1 ENDP  
_text ENDS  
END  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)