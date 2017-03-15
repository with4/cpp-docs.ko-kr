---
title: "컴파일러 오류 C2885 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2885"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2885"
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 컴파일러 오류 C2885
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::identifier' : 비클래스 범위의 using 선언이 잘못되었습니다.  
  
 [using](../../cpp/using-declaration.md) 선언을 잘못 사용했습니다.  
  
## 예제  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, 중첩된 형식에 대해 `using` 선언을 사용하는 것이 더 이상 유효하지 않으며 중첩된 형식에 대해 만드는 각 참조를 명시적으로 한정하거나, 형식을 네임스페이스에 넣거나, typedef를 만들어야 한다는 컴파일러 규칙의 결과로 발생할 수 있습니다.  
  
 다음 샘플에서는 C2885 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## 예제  
 `using` 키워드를 클래스 멤버와 함께 사용하는 경우 C\+\+에서는 다른 클래스\(파생 클래스\) 내부에 해당 멤버를 정의해야 합니다.  
  
 다음 샘플에서는 C2885 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```