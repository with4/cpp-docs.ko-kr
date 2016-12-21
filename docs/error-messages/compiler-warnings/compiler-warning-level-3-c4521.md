---
title: "컴파일러 경고 (수준 3) C4521 | Microsoft Docs"
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
  - "C4521"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4521"
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4521
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 복사 생성자를 여러 개 지정했습니다.  
  
 클래스에 단일 형식의 복사 생성자가 여러 개 있으므로  이 경고는 정보를 제공하기 위한 것입니다. 프로그램에서는 생성자를 호출할 수 있습니다.  
  
 이 경고가 나타나지 않도록 하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  
  
## 예제  
 다음 샘플에서는 C4521 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```