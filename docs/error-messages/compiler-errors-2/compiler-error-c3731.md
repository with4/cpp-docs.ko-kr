---
title: "컴파일러 오류 C3731 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3731
dev_langs: C++
helpviewer_keywords: C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c285e8d63787bc69600784aede49fe93f4e4bb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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