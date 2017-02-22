---
title: "vector::vector(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector 멤버[STL/CLR]"
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::vector(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 개체를 만듭니다.  
  
## 구문  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### 매개 변수  
 count  
 Number of elements to insert.  
  
 first  
 Beginning of range to insert.  
  
 last  
 End of range to insert.  
  
 right  
 Object or range to insert.  
  
 val  
 Value of the element to insert.  
  
## 설명  
 The constructor:  
  
 `vector();`  
  
 initializes the controlled sequence with no elements.  You use it to specify an empty initial controlled sequence.  
  
 The constructor:  
  
 `vector(vector<Value>% right);`  
  
 initializes the controlled sequence with the sequence `[``right``.`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``.`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the vector object `right`.  
  
 The constructor:  
  
 `vector(vector<Value>^ right);`  
  
 initializes the controlled sequence with the sequence `[``right``->`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``->`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the vector object whose handle is `right`.  
  
 The constructor:  
  
 `explicit vector(size_type count);`  
  
 initializes the controlled sequence with `count` elements each with value `value_type()`.  You use it to fill the container with elements all having the default value.  
  
 The constructor:  
  
 `vector(size_type count, value_type val);`  
  
 initializes the controlled sequence with `count` elements each with value `val`.  You use it to fill the container with elements all having the same value.  
  
 The constructor:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 initializes the controlled sequence with the sequence `[``first``,` `last``)`.  You use it to make the controlled sequence a copy of another sequence.  
  
 The constructor:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 initializes the controlled sequence with the sequence designated by the enumerator `right`.  You use it to make the controlled sequence a copy of another sequence described by an enumerator.  
  
## 예제  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0**  
 **x x x x x x**  
 **x x x x x**  
 **x x x x x x**  
 **x x x x x x**  
 **x x x x x x**   
## 요구 사항  
 **Header:** \<cliext\/vector\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [vector](../dotnet/vector-stl-clr.md)   
 [vector::assign](../dotnet/vector-assign-stl-clr.md)   
 [vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)