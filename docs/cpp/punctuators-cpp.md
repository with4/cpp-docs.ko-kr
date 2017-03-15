---
title: "C++ 문장 부호 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - ";"
  - ","
  - "{"
  - "}"
  - "("
  - ")"
  - "["
  - "]"
  - "!"
  - "%"
  - "^"
  - "*"
  - """
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문장 부호"
ms.assetid: 1521564c-a977-488a-9490-068079897592
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 문장 부호
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+의 문장 부호는 컴파일러에서 구문 및 의미 체계를 의미하지만 스스로 값을 생성하는 연산을 지정하지 않습니다.  또한 일부 단독 또는 조합 문장 기호는 C\+\+ 연산자가 될 수도 있고 전처리기에 중요할 수도 있습니다.  
  
 다음 문자는 모두 문장 부호로 간주됩니다.  
  
```  
! % ^ & * ( ) – + = { } | ~  
[ ] \ ; ' : " < > ? , . / #  
```  
  
 문장 부호 **\[ \]**, **\( \)** 및 **{ }**는 [변환 단계](../preprocessor/phases-of-translation.md) 4 뒤에 위치해야 합니다.  
  
## 참고 항목  
 [어휘 규칙](../cpp/lexical-conventions.md)