---
title: 컴파일러 오류 C3731 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3731
dev_langs:
- C++
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7b87b59fa7a3e3695da88b5ddb30a84837f6e60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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