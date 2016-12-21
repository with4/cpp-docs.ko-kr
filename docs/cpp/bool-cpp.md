---
title: "bool (C++) | Microsoft Docs"
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
  - "bool_cpp"
  - "bool"
  - "__BOOL_DEFINED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__BOOL_DEFINED 매크로"
  - "bool 키워드[C++]"
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bool (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 키워드는 기본 제공 형식입니다.  이 형식의 변수는 [true](../cpp/true-cpp.md) 및 [false](../cpp/false-cpp.md) 값을 가질 수 있습니다.  조건식은 `bool` 형식이며 `bool` 형식의 값을 갖습니다.  예를 들어, `i!=0`은 `i`의 값에 따라 **true** 또는 **false** 값을 갖습니다.  
  
 **true** 및 **false** 값은 다음 관계를 갖습니다.  
  
```  
!false == true  
!true == false  
```  
  
 다음 문에서  
  
```  
if (condexpr1) statement1;   
```  
  
 `condexpr1`이 **true**이면 `statement1`이 항상 실행되고 `condexpr1`이 **false**이면 `statement1`이 실행되지 않습니다.  
  
 후위 또는 접두사 `++` 연산자가 `bool` 형식의 변수에 적용되면 변수가 **true**로 설정됩니다.  후위 또는 접두사 `--` 연산자를 이 형식의 변수에 적용할 수 없습니다.  
  
 `bool` 형식은 정수 계열 확장에 참여합니다.  **false**가 0이 되고 **true**가 1이 되면 `bool` 형식의 r\-value를 `int` 형식의 r\-value로 변환할 수 있습니다.  `bool`이 고유한 형식으로 오버로드 확인에 참여합니다.  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [기본 형식](../cpp/fundamental-types-cpp.md)