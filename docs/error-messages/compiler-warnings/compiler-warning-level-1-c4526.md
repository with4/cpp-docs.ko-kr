---
title: "컴파일러 경고 (수준 1) C4526 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4526"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4526"
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4526
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 정적 멤버 함수가 'virtual function' 가상 함수를 재정의할 수 없습니다. 재정의가 무시되고 가상 함수는 숨겨집니다.  
  
 멤버 함수는 가상이면서 동시에 정적으로 만들 수 없으므로 정적 멤버 함수에서 가상 함수를 재정의하라는 조건을 충족할 수 없습니다.  
  
 다음 코드에서는 C4526 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 문제를 해결할 수 있는 방법은 다음과 같습니다.  
  
-   함수에서 기본 클래스 가상 함수를 재정의하려고 했다면 static 지정자를 제거합니다.  
  
-   함수를 정적 멤버 함수로 만들려고 했다면 이름을 변경하여 기본 클래스 가상 함수와 충돌하지 않도록 합니다.