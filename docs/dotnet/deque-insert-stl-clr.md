---
title: "deque::insert(STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert 멤버[STL/CLR]"
ms.assetid: a3b86c46-e6a8-42d0-b642-5a8f05ddd68c
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::insert(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Adds elements at a specified position.  
  
## 구문  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### 매개 변수  
 count  
 Number of elements to insert.  
  
 first  
 Beginning of range to insert.  
  
 last  
 End of range to insert.  
  
 right  
 Enumeration to insert.  
  
 val  
 Value of the element to insert.  
  
 where  
 Where in container to insert before.  
  
## 설명  
 Each of the member functions inserts, before the element pointed to by `where` in the controlled sequence, a sequence specified by the remaining operands.  
  
 The first member function inserts an element with value `val` and returns an iterator that designates the newly inserted element.  You use it to insert a single element before a place designated by an iterator.  
  
 두 번째 멤버 함수는  `val` 의  `count`  요소의 반복을 삽입합니다.  You use it to insert zero or more contiguous elements which are all copies of the same value.  
  
 If `InIt` is an integer type, the third member function behaves the same as `insert(``where``, (size_type)``first``, (value_type)``last``)`.  Otherwise, it inserts the sequence `[``first``,` `last``)`.  You use it to insert zero or more contiguous elements copied from another sequence.  
  
 The fourth member function inserts the sequence designated by the `right`.  You use it to insert a sequence described by an enumerator.  
  
 When inserting a single element, the number of element copies is linear in the number of elements between the insertion point and the nearer end of the sequence. \(When inserting one or more elements at either end of the sequence, no element copies occur.\) If `InIt` is an input iterator, the third member function effectively performs a single insertion for each element in the sequence.  Otherwise, when inserting `N` elements, the number of element copies is linear in `N` plus the number of elements between the insertion point and the nearer end of the sequence.  
  
## 예제  
  
```  
// cliext_deque_insert.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**insert\(begin\(\)\+1, L'x'\) \= x**  
 **a x b c**  
 **y y**  
 **y y a x b**  
 **a x b c y y a x b**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)