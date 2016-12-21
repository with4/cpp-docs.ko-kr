---
title: "auto_handle::swap | Microsoft Docs"
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
  - "msclr::auto_handle::swap"
  - "auto_handle.swap"
  - "auto_handle::swap"
  - "msclr..auto_handle.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::swap"
ms.assetid: 3ebf82d7-9b69-4a72-a22d-69b4f640f9b0
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Swaps objects with another `auto_handle`.  
  
## 구문  
  
```  
void swap(  
   auto_handle<_element_type> % _right  
);  
```  
  
#### 매개 변수  
 `_right`  
 The `auto_handle` with which to swap objects.  
  
## 예제  
  
```  
// msl_auto_handle_swap.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
  **s1 \= 'string one', s2 \= 'string two'**  
**s1 \= 'string two', s2 \= 'string one'**   
## 요구 사항  
 **Header file** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_handle 멤버](../dotnet/auto-handle-members.md)   
 [swap 함수\(auto\_handle\)](../dotnet/swap-function-auto-handle.md)