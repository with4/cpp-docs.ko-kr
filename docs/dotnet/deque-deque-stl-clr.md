---
title: "deque::deque(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "deque 멤버[STL/CLR]"
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# deque::deque(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 개체를 만듭니다.  
  
## 구문  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `deque();`  
  
 initializes the controlled sequence with no elements.  You use it to specify an empty initial controlled sequence.  
  
 The constructor:  
  
 `deque(deque<Value>% right);`  
  
 initializes the controlled sequence with the sequence `[``right``.`[deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` `right``.`[deque::end](../dotnet/deque-end-stl-clr.md)`())`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the deque object `right`.  
  
 The constructor:  
  
 `deque(deque<Value>^ right);`  
  
 initializes the controlled sequence with the sequence `[``right``->`[deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` `right``->`[deque::end](../dotnet/deque-end-stl-clr.md)`())`.  You use it to specify an initial controlled sequence that is a copy of the sequence controlled by the deque object whose handle is `right`.  
  
 The constructor:  
  
 `explicit deque(size_type count);`  
  
 initializes the controlled sequence with `count` elements each with value `value_type()`.  You use it to fill the container with elements all having the default value.  
  
 The constructor:  
  
 `deque(size_type count, value_type val);`  
  
 initializes the controlled sequence with `count` elements each with value `val`.  You use it to fill the container with elements all having the same value.  
  
 The constructor:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 initializes the controlled sequence with the sequence `[``first``,` `last``)`.  You use it to make the controlled sequence a copy of another sequence.  
  
 The constructor:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 initializes the controlled sequence with the sequence designated by the enumerator `right`.  You use it to make the controlled sequence a copy of another sequence described by an enumerator.  
  
## 예제  
  
```  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
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
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)   
 [deque::generic\_container](../dotnet/deque-generic-container-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)