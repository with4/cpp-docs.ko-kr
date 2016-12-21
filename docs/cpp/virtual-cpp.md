---
title: "virtual (C++) | Microsoft Docs"
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
  - "virtual_cpp"
  - "virtual"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기본 클래스, virtual"
  - "가상 기본 클래스, 선언"
  - "가상 함수, 선언"
  - "virtual 키워드[C++]"
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# virtual (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`virtual` 키워드는 가상 함수 또는 가상 기본 클래스를 선언합니다.  
  
## 구문  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### 매개 변수  
 `type-specifiers`  
 가상 멤버 함수의 반환 형식을 지정합니다.  
  
 `member-function-declarator`  
 멤버 함수를 선언합니다.  
  
 `access-specifier`  
 기본 클래스 `public`, `protected` 또는 `private`에 대한 액세스 수준을 정의합니다.  `virtual` 키워드 앞이나 뒤에 나타날 수 있습니다.  
  
 `base-class-name`  
 이전에 선언된 클래스 형식을 식별합니다.  
  
## 설명  
 자세한 내용은 [가상 함수](../cpp/virtual-functions.md) 및 [가상 기본 클래스](../misc/virtual-base-classes.md)를 참조하세요.  
  
 또한 키워드 [class](../cpp/class-cpp.md), [private](../cpp/private-cpp.md), [public](../cpp/public-cpp.md) 및 [protected](../cpp/protected-cpp.md)를 참조하세요.  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)