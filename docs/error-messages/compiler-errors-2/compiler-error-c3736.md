---
title: "컴파일러 오류 C3736 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3736"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3736"
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3736
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': 메서드이거나, 관리되는 이벤트의 경우 데이터 멤버여야 합니다.  
  
 Native 및 COM 이벤트는 메서드여야 합니다. .NET 이벤트는 데이터 멤버도 가능합니다.  
  
 다음 샘플에서는 C3736 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3736.cpp  
struct A {  
   __event int e();  
};  
  
struct B {  
   int f;   // C3736  
   // The following line resolves the error.  
   // int f();  
   B(A* a) {  
      __hook(&A::e, a, &B::f);  
   }  
};  
  
int main() {  
}  
```