---
title: "컴파일러 오류 C2276 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2276
dev_langs:
- C++
helpviewer_keywords:
- C2276
ms.assetid: 62005ad9-6cb9-4b1f-965d-b875adaf695e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df0ef658b55ac4d94c30d4c7f2338a0f22f6947e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2276"></a>컴파일러 오류 C2276
'operator': 바인딩된 멤버 함수 식에 잘못 된 작업  
  
 포인터-멤버를 만들려면 구문 사용 하 여 문제를 발견 하는 컴파일러.  
  
 다음 샘플에서는 C2276 오류가 생성 됩니다.  
  
```  
// C2276.cpp  
class A {  
public:  
   int func(){return 0;}  
} a;  
  
int (*pf)() = &a.func;   // C2276  
// try the following line instead  
// int (A::*pf3)() = &A::func;  
  
class B {  
public:  
   void mf() {  
      &this -> mf;   // C2276  
      // try the following line instead  
      // &B::mf;  
   }  
};  
  
int main() {  
   A a;  
   &a.func;   // C2276  
   // try the following line instead  
   // &A::func;  
}  
```