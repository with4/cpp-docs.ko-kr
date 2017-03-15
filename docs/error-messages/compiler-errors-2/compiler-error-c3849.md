---
title: "컴파일러 오류 C3849 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3849"
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 형식의 식에서 함수 형식을 호출할 때 모든 number이\(가\) 사용 가능한 연산자 오버로드에 대해 const 및\/또는 volatile 한정자가 손실됩니다.  
  
 지정된 const\-volatile 형식의 변수는 const\-volatile 한정이 같거나 더 큰 멤버 함수만 호출할 수 있습니다.  
  
 이 오류를 해결하려면 적절한 멤버 함수를 제공하십시오.  변환으로 인해 한정이 손실될 경우에는 const 또는 volatile로 한정된 개체에 대해 변환을 수행할 수 없습니다.  한정자를 얻을 수는 있지만 변환 중 한정자가 손실될 수 있습니다.  
  
 다음 샘플에서는 C3849 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C3849.cpp  
void glbFunc3(int i, char c)  
{  
   i;  
}  
typedef void (* pFunc3)(int, char);  
  
void glbFunc2(int i)  
{  
   i;  
}  
  
typedef void (* pFunc2)(int);  
  
void glbFunc1()  
{  
}  
typedef void (* pFunc1)();  
  
struct S4  
{  
   operator ()(int i)  
   {  
      i;  
   }  
  
   operator pFunc1() const  
   {  
      return &glbFunc1;  
   }  
  
   operator pFunc2() volatile  
   {  
      return &glbFunc2;  
   }  
  
   operator pFunc3()  
   {  
      return &glbFunc3;  
   }  
  
   // operator pFunc1() const volatile  
   // {  
   //    return &glbFunc1;  
   // }  
};  
  
int main()  
{  
   // Cannot call any of the 4 overloads of "operator ()(.....)" and   
   // "operator pFunc()" because none is declared as "const volatile"  
   const volatile S4 s4;  // can only call cv member functions of S4  
   s4();   // C3849 to resolve, uncomment member function  
}  
```