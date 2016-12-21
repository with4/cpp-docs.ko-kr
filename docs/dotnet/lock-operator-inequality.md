---
title: "lock::operator!= | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "lock.operator!="
  - "msclr.lock.operator!="
  - "msclr::lock::operator!="
  - "lock::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::operator!="
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
caps.latest.revision: 6
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock::operator!=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inequality operator.  
  
## 구문  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### 매개 변수  
 `t`  
 The object to compare for inequality.  
  
## 반환 값  
 Returns `true` if `t` differs from the lock's object, `false` otherwise.  
  
## 예제  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
  **Inequal\!**   
## 요구 사항  
 **Header file** \<msclr\\lock.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [lock 멤버](../dotnet/lock-members.md)   
 [lock::operator\=\=](../dotnet/lock-operator-equality.md)