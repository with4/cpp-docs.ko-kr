---
title: ".PUSHFRAME | Microsoft Docs"
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
  - ".PUSHFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHFRAME directive"
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성 하는 `UWOP_PUSH_MACHFRAME` 코드 항목을 해제 합니다.  경우 선택적 `code` 지정 해제 코드 엔트리도 1 한정자가 지정 됩니다.  그렇지 않으면 한정자로 0이 지정됩니다.  
  
## 구문  
  
```  
.PUSHFRAME [code]  
```  
  
## 설명  
 .PUSHFRAME ml64.exe 사용자가 지정 하는 방법 프레임 기능을 해제 하 고 프롤로그에서 확장에 사용할 수 있습니다에서 [PROC](../../assembler/masm/proc.md) 프레임 선언에는 [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다.  이러한 지시문 코드를 생성 하지 않습니다. 생성만 `.xdata` 및 `.pdata`.  .PUSHFRAME 해제 되지 않도록 하는 작업을 실제로 구현 지침으로 표시 합니다.  해제 지시문과 계약을 확인 하려면 매크로 해제 합니다 의미입니다 코드를 래핑하는 것이 좋습니다.  
  
 자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)를 참조하십시오.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)