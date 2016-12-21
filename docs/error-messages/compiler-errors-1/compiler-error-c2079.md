---
title: "컴파일러 오류 C2079 | Microsoft Docs"
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
  - "C2079"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2079"
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2079
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'은\(는\) 정의되지 않은 클래스\/구조체\/공용 구조체 'name'을\(를\) 사용합니다.  
  
 지정한 식별자는 정의되지 않은 클래스, 구조체 또는 공용 구조체입니다.  
  
 이 오류는 익명 공용 구조체를 초기화하는 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2079 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 C2079는 해당 전달 선언이 범위에만 있는 형식의 스택에 개체를 선언하려는 경우에도 발생할 수 있습니다.  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```