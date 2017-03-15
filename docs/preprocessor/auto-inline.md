---
title: "auto_inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_inline_CPP"
  - "vc-pragma.auto_inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_inline pragma"
  - "pragma, auto_inline"
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# auto_inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**off**가 지정된 범위 내에서 정의된 모든 함수를 자동 인라인 확장의 후보에서 제외합니다.  
  
## 구문  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## 설명  
 **auto\_inline** pragma를 사용하려면 함수 정의 내부가 아니라 앞과 바로 뒤에 pragma를 배치합니다.  pragma가 표시된 후 첫 번째 함수 정의에서 pragma가 적용됩니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)