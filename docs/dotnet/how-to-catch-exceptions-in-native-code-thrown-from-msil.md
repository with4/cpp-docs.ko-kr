---
title: "방법: 네이티브 코드에서 MSIL이 throw한 예외 catch | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예외 catch, MSIL에서 throw"
  - "예외, catch"
  - "MSIL, 네이티브 코드에서 예외 catch"
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 네이티브 코드에서 MSIL이 throw한 예외 catch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In native code, you can catch native C\+\+ exception from MSIL.  You can catch CLR exceptions with `__try` and `__except`.  
  
 자세한 내용은 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md) 및 [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md)를 참조하십시오.  
  
## 예제  
 The following sample defines a module with two functions, one that throws a native exception, and another that throws an MSIL exception.  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## 예제  
 The following sample defines a module that catches a native and MSIL exception.  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
  **error**  
**caught an exception**   
## 참고 항목  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)