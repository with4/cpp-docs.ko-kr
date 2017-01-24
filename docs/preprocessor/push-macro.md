---
title: "push_macro | Microsoft Docs"
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
  - "vc-pragma.push_macro"
  - "push_macro_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pragma, push_macro"
  - "push_macro pragma"
ms.assetid: ac89efc9-afd1-4dfe-bfd1-497229b3e81d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# push_macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 매크로에 대해 스택의 맨 위에 있는 *macro\_name* 매크로의 값을 저장합니다.  
  
## 구문  
  
```  
  
#pragma push_macro("  
macro_name  
")  
  
```  
  
## 설명  
 *macro\_name*의 값을 **pop\_macro**와 함께 검색할 수 있습니다.  
  
 샘플로 [pop\_macro](../preprocessor/pop-macro.md)를 참조하십시오.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)