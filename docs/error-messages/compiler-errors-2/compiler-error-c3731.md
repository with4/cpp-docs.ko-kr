---
title: "컴파일러 오류 C3731 | Microsoft Docs"
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
  - "C3731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3731"
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function1' 이벤트와 'function2' 처리기가 호환되지 않습니다. 이벤트 소스와 이벤트 처리기는 같은 이벤트 형식을 사용해야 합니다.  
  
 이벤트 소스와 이벤트 수신자의 형식은 동일해야 합니다\(예: `native`와`com` types\)  이 오류를 해결하려면 이벤트 소스와 이벤트 처리기의 형식을 일치시키십시오.  
  
 다음 샘플에서는 C3731 오류가 발생하는 경우를 보여 줍니다.  
  
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