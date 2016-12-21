---
title: "컴파일러 오류 C2701 | Microsoft Docs"
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
  - "C2701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2701"
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 템플릿은\(는\) 지역 클래스의 friend가 될 수 없습니다.  
  
 지역 클래스에서는 템플릿 함수를 friend 함수로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2701 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2701.cpp  
// compile with: /c  
template<typename T>   // OK  
void f1(const T &);  
  
void MyFunction() {  
   class MyClass {  
      template<typename T> friend void f2(const T &);   // C2701  
   };  
}  
```