---
title: "vector::const_iterator(STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::const_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_iterator 멤버[STL/CLR]"
ms.assetid: 09c0ae0b-248b-463c-8f57-59c77eba1eaa
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::const_iterator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스에 대한 상수 반복기의 형식입니다.  
  
## 구문  
  
```  
typedef T2 const_iterator;  
```  
  
## 설명  
 형식은 제어된 시퀀스를 위해 상수 랜덤 액세스 반복기의 역할을 할 수 있는 지정되지 않은 형식 `T2`의 개체를 설명합니다.  
  
## 예제  
  
```  
// cliext_vector_const_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 요구 사항  
 **Header:** \<cliext\/vector\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [vector](../dotnet/vector-stl-clr.md)   
 [vector::iterator](../dotnet/vector-iterator-stl-clr.md)