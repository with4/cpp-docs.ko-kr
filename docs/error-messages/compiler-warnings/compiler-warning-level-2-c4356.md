---
title: "컴파일러 경고 (수준 2) C4356 | Microsoft Docs"
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
  - "C4356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4356"
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 정적 데이터 멤버는 파생 클래스를 통해 초기화할 수 없습니다.  
  
 정적 데이터 멤버 초기화의 형식이 올바르지 않습니다.  컴파일러에서는 이러한 초기화를 허용합니다.  
  
 이는 Visual C\+\+ .NET 2003 컴파일러의 주요 변경 내용입니다.  
  
 모든 버전의 Visual C\+\+에서 코드가 똑같은 방식으로 작동하도록 하려면 기본 클래스를 통해 멤버를 초기화하십시오.  
  
 이 경고가 나타나지 않도록 하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  
  
 다음 샘플에서는 C4356 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```