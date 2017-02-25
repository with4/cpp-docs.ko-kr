---
title: "컴파일러 경고 (수준 3) C4522 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4522"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4522"
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 3) C4522
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 할당 연산자를 여러 개 지정했습니다.  
  
 클래스에 단일 형식의 할당 연산자가 여러 개 있습니다.  이 경고는 정보를 제공하기 위한 것입니다. 프로그램에서는 생성자를 호출할 수 있습니다.  
  
 이 경고가 나타나지 않도록 하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  
  
## 예제  
 다음 샘플에서는 C4522 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4522.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }  
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522  
};  
  
int main() {  
   A o1, o2;  
   o2 = o1;  
   const A o3;  
   o1 = o3;  
}  
```