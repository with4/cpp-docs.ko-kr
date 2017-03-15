---
title: "queue::container_type(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::container_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "container_type 멤버[STL/CLR]"
ms.assetid: 118168f9-e5ed-47e2-a4f5-26b0b56e41e1
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# queue::container_type(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 컨테이너의 형식입니다.  
  
## 구문  
  
```  
typedef Container value_type;  
```  
  
## 설명  
 형식은 템플릿 매개 변수 `Container`와 동의어입니다.  
  
## 예제  
  
```  
// cliext_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Myqueue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::get\_container](../dotnet/queue-get-container-stl-clr.md)