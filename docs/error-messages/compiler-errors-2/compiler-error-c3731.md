---
title: "컴파일러 오류 C3731 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3731
dev_langs:
- C++
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ac117c6c2020607d5b2d15b0229eaa045a22ec99
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3731"></a>컴파일러 오류 C3731
'function1' 호환 되지 않는 이벤트 및 이벤트 처리기 'function2'; 이벤트 소스와 이벤트 처리기에는 동일한 형식 이어야 합니다.  
  
 이벤트 소스와 이벤트 수신자는 형식이 동일해야 합니다(예:`native` 및 `com` 형식). 이 오류를 해결 하려면 이벤트 소스와 일치 하는 이벤트 처리기의 형식 이어야 합니다.  
  
 다음 샘플에서는 C3731 오류가 생성 됩니다.  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```
