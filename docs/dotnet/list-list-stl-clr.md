---
title: "list::list(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list 멤버[STL/CLR]"
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::list(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 개체를 만듭니다.  
  
## 구문  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `list();`  
  
 initializes the controlled sequence with no elements.  You use it to specify an empty initial controlled sequence.  
  
 The constructor:  
  
 `list(list<Value>% right);`  
  
 initializes the controlled sequence with the sequence `[``right``.`[list::begin](../dotnet/list-begin-stl-clr.md)`(),` `right``.`[list::end](../dotnet/list-end-stl-clr.md)`())`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the list object `right`.  
  
 The constructor:  
  
 `list(list<Value>^ right);`  
  
 initializes the controlled sequence with the sequence `[``right``->`[list::begin](../dotnet/list-begin-stl-clr.md)`(),` `right``->`[list::end](../dotnet/list-end-stl-clr.md)`())`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the list object whose handle is `right`.  
  
 The constructor:  
  
 `explicit list(size_type count);`  
  
 initializes the controlled sequence with `count` elements each with value `value_type()`.  You use it to fill the container with elements all having the default value.  
  
 The constructor:  
  
 `list(size_type count, value_type val);`  
  
 initializes the controlled sequence with `count` elements each with value `val`.  You use it to fill the container with elements all having the same value.  
  
 The constructor:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 initializes the controlled sequence with the sequence `[``first``,` `last``)`.  You use it to make the controlled sequence a copy of another sequence.  
  
 The constructor:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 initializes the controlled sequence with the sequence designated by the enumerator `right`.  You use it to make the controlled sequence a copy of another sequence described by an enumerator.  
  
## 예제  
  
```  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
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
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)   
 [list::generic\_container](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator\=](../dotnet/list-operator-assign-stl-clr.md)