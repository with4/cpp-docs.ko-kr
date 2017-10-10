---
title: "컴파일러 오류 C2171 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2171
dev_langs:
- C++
helpviewer_keywords:
- C2171
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 08b5b7c00ed54b14597995d8923a5c36c7b87289
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2171"></a>컴파일러 오류 C2171
'operator': 'type' 형식의 피연산자에는 맞지 않습니다.  
  
 단항 연산자가 잘못된 피연산자 형식과 함께 사용됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2171을 생성합니다.  
  
```  
// C2171.cpp  
int main() {  
   double d, d1;  
   d = ~d1;   // C2171  
  
   // OK  
   int d2 = 0, d3 = 0;  
   d2 = ~d3;  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2171을 생성합니다.  
  
```  
// C2171_b.cpp  
// compile with: /c  
class A {  
public:  
   A() { STF( &A::D ); }  
  
   void D() {}  
   void DTF() {  
      (*TF)();   // C2171  
      (this->*TF)();   // OK  
   }  
  
   void STF(void (A::*fnc)()) {  
      TF = fnc;  
   }  
  
private:  
   void (A::*TF)();  
};  
```
