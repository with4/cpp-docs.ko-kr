---
title: "컴파일러 경고 (수준 1) C4661 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4661"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4661"
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4661
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 명시적 템플릿 인스턴스화 요청에 대한 적절한 정의를 제공하지 않았습니다.  
  
 템플릿 클래스의 멤버를 정의하지 않았습니다.  
  
## 예제  
  
```  
// C4661.cpp  
// compile with: /W1 /LD  
template<class T> class MyClass {  
public:  
   void i();   // declaration but not definition  
};  
template MyClass< int >;  // C4661  
```