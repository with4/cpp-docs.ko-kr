---
title: 컴파일러 오류 C3849 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3849
dev_langs:
- C++
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e771e67e3432273c8b3880b44d04e4a17217960b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270966"
---
# <a name="compiler-error-c3849"></a>컴파일러 오류 C3849
함수 형식을 호출할 'type' 형식의 식에는 모든 숫자의 사용 가능한 연산자 오버 로드에 대 한 const 및/또는 volatile 한정자가 손실  
  
 지정 된 const volatile 형식의 변수에 호출할 수 있습니다 멤버 이상 const-volatile 한정자 사용 함수를 정의 합니다.  
  
 이 오류를 해결 하려면 적절 한 멤버 함수를 제공 합니다. 변환으로 인해 자격이 손실 변환을 const 또는 volatile 한정 된 개체에서 실행할 수 없습니다. 한정자를 얻을 수 있지만 경우 변환에는 한정자를 비워 둘 수 없는 합니다.  
  
 다음 샘플에서는 c3849:  
  
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