---
title: "전처리 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연산자[C++], 전처리기"
  - "전처리 연산자"
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 전처리 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

4개의 특정 전처리기 연산자는 `#define` 지시문 컨텍스트에 사용됩니다\(요약은 각각 다음 목록 참조\).  stringizing, charizing 및 토큰 전달 연산자는 다음 세 단원에서 설명합니다.  **defined** 연산자에 대한 자세한 내용은 [\#if, \#elif, \#else 및 \#endif 지시문](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)을 참조하십시오.  
  
|연산자|작업|  
|---------|--------|  
|[문자열화 연산자\(\#\)](../preprocessor/stringizing-operator-hash.md)|해당하는 실제 인수가 큰따옴표로 묶이도록 합니다.|  
|[Charizing 연산자\(\#@\)](../preprocessor/charizing-operator-hash-at.md)|해당 인수를 작은 따옴표로 묶고 문자로 취급하는 것이 원인입니다\(Microsoft 전용\)|  
|[토큰 붙여넣기 연산자\(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)|실제 인수로 사용되는 토큰이 다른 토큰을 형성하기 위해 연결될 수 있도록 합니다.|  
|[사용자 정의 연산자](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|특정 매크로 지시문으로 복합 식 작성을 단순화합니다.|  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)   
 [미리 정의된 매크로](../preprocessor/predefined-macros.md)   
 [C\/C\+\+ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)