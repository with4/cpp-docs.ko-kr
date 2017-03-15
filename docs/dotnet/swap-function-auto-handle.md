---
title: "swap 함수(auto_handle) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::swap"
  - "msclr.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap 함수"
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# swap 함수(auto_handle)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Swaps objects between one `auto_handle` and another.  
  
## 구문  
  
```  
template<typename _element_type>  
void swap(  
   auto_handle<_element_type> % _left,  
   auto_handle<_element_type> % _right  
);  
```  
  
#### 매개 변수  
 `_left`  
 `auto_handle`입니다.  
  
 `_right`  
 다른 `auto_handle`입니다.  
  
## 예제  
  
```  
// msl_swap_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   swap( s1, s2 );  
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
 [auto\_handle](../dotnet/auto-handle.md)   
 [auto\_handle::swap](../dotnet/auto-handle-swap.md)