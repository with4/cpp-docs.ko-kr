---
title: "list::merge(STL/CLR) | Microsoft Docs"
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
  - "cliext::list::merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "merge 멤버[STL/CLR]"
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::merge(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

순서가 지정된 두 개의 제어되는 시퀀스를 병합합니다.  
  
## 구문  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### 매개 변수  
 pred  
 Comparer for element pairs.  
  
 right  
 Container to merge in.  
  
## 설명  
 The first member function removes all elements from the sequence controlled by `right` and insert them in the controlled sequence.  Both sequences must be previously ordered by `operator<` \-\- elements must not decrease in value as you progress through either sequence.  The resulting sequence is also ordered by `operator<`.  You use this member function to merge two sequences that increase in value into a sequence that also increases in value.  
  
 The second member function behaves the same as the first, except that the sequences are ordered by `pred` \-\- `pred``(X, Y)` must be false for any element `X` that follows element `Y` in the sequence.  You use it to merge two sequences ordered by a predicate function or delegate that you specify.  
  
 Both functions perform a stable merge \-\- no pair of elements in either of the original controlled sequences is reversed in the resulting controlled sequence.  Also, if a pair of elements `X` and `Y` in the resulting controlled sequence has equivalent ordering \-\- `!(X < Y) && !(X < Y)` \-\- an element from the original controlled sequence appears before an element from the sequence controlled by `right`.  
  
## 예제  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a c e**  
 **b d f**  
 **a b c d e f**  
**c2.size\(\) \= 0**  
 **e c a**  
 **f e d c b a**  
 **f e e d c c b a a**  
**c1.size\(\) \= 0**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)   
 [list::splice](../dotnet/list-splice-stl-clr.md)