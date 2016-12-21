---
title: "컴파일러 오류 C2073 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2073"
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 부분적으로 초기화된 배열의 요소에는 기본 생성자가 있어야 합니다.  
  
 사용자 정의 형식이나 상수의 배열에 대한 이니셜라이저가 거의 지정되어 있지 않습니다.  배열 멤버에 대한 명시적 이니셜라이저 및 해당 생성자가 지정되지 않은 경우에는 기본 생성자를 제공해야 합니다.  
  
 다음 샘플에서는 C2073 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2073.cpp  
class A {  
public:  
   A( int );   // constructor for ints only  
};  
A a[3] = { A(1), A(2) };   // C2073, no default constructor  
```  
  
```  
// C2073b.cpp  
// compile with: /c  
class B {  
public:  
   B();   // default constructor declared  
   B( int );  
};  
B b[3] = { B(1), B(2) };   // OK  
```