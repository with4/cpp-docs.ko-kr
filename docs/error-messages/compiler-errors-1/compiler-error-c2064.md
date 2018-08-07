---
title: 컴파일러 오류 C2064 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2064
dev_langs:
- C++
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3e5e21d7c33c84bb531b53c08aefbfce9dc7fd8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167283"
---
# <a name="compiler-error-c2064"></a>컴파일러 오류 C2064
항은 N개의 인수를 받아들이는 함수로 계산되지 않습니다.  
  
 식을 통해 함수가 호출됩니다. 식은 지정된 수의 인수를 사용하는 함수에 대한 포인터로 계산되지 않습니다.  
  
 이 예제에서는 코드가 비함수를 함수로 호출하려고 합니다. 다음 샘플에서는 C2064 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2064.cpp  
int i, j;  
char* p;  
void func() {  
   j = i();    // C2064, i is not a function  
   p();        // C2064, p doesn't point to a function  
}  
```  
  
 개체 인스턴스의 컨텍스트에서 비정적 멤버 함수에 대한 포인터를 호출해야 합니다. 다음 샘플에서는 C2064 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2064b.cpp  
struct C {  
   void func1(){}  
   void func2(){}  
};  
  
typedef void (C::*pFunc)();  
  
int main() {  
   C c;  
   pFunc funcArray[2] = {&C::func1, &C::func2};  
   (funcArray[0])();    // C2064   
   (c.*funcArray[0])(); // OK - function called in instance context  
}  
  
```  
  
 클래스 내에서 멤버 함수 포인터도 호출 개체 컨텍스트를 나타내야 합니다. 다음 샘플에서는 C2064 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2064d.cpp  
// Compile by using: cl /c /W4 C2064d.cpp  
struct C {  
   typedef void (C::*pFunc)();  
   pFunc funcArray[2];  
   void func1(){}  
   void func2(){}  
   C() {  
      funcArray[0] = &C::func1;  
      funcArray[1] = &C::func2;  
   }  
   void func3() {  
      (funcArray[0])();   // C2064  
      (this->*funcArray[0])(); // OK - called in this instance context  
   }  
};  
```