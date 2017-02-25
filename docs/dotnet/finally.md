---
title: "finally | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "finally 키워드[C++]"
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# finally
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In addition to `try` and `catch` clauses, CLR exception handling supports a `finally` clause.  The semantics are identical to the `__finally` block in structured exception handling \(SEH\).  A `__finally` block can follow a `try` or `catch` block.  
  
## 설명  
 The purpose of the `finally` block is to clean up any resources left after the exception occurred.  Note that the `finally` block is always executed, even if no exception was thrown.  The `catch` block is only executed if a managed exception is thrown within the associated `try` block.  
  
 `finally`는 대\/소문자를 구분하는 키워드입니다. 자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 The following example demonstrates a simple `finally` block:  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
  **in catch**  
**MyException**  
**in finally**   
## 참고 항목  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)