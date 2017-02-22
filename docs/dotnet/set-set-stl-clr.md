---
title: "set::set(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set 멤버[STL/CLR]"
ms.assetid: 0cce8501-92ed-431c-b711-14e0b7be7375
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# set::set(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 개체를 만듭니다.  
  
## 구문  
  
```  
set();  
explicit set(key_compare^ pred);  
set(set<Key>% right);  
set(set<Key>^ right);  
template<typename InIter>  
    setset(InIter first, InIter last);  
template<typename InIter>  
    set(InIter first, InIter last,  
        key_compare^ pred);  
set(System::Collections::Generic::IEnumerable<GValue>^ right);  
set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### 매개 변수  
 first  
 삽입할 범위의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 pred  
 제어된 시퀀스를 위한 술부의 정렬입니다.  
  
 right  
 삽입할 범위 또는 개체입니다.  
  
## 설명  
 생성자:  
  
 `set();`  
  
 요소가 없는 제어된 시퀀스를 기본 술어 정렬 `key_compare()`로 초기화합니다.  빈 초기 제어된 시퀀스를 기본 술어 정렬로 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `explicit set(key_compare^ pred);`  
  
 요소가 없는 제어된 시퀀스를 술어 정렬 `pred`로 초기화합니다.  빈 초기 제어된 시퀀스를 지정된 술어 정렬로 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `set(set<Key>% right);`  
  
 시퀀스 `[``right``.`[set::begin](../dotnet/set-begin-stl-clr.md)`(),` `right``.`[set::end](../dotnet/set-end-stl-clr.md)`())`를 포함한 제어된 시퀀스를 기본 술어 정렬로 초기화합니다.  개체 집합`right`에 의해 제어된 시퀀스의 복사본인 초기 제어된 시퀀스를 기본 술어 정렬로 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `set(set<Key>^ right);`  
  
 시퀀스 `[``right``->`[set::begin](../dotnet/set-begin-stl-clr.md)`(),` `right``->`[set::end](../dotnet/set-end-stl-clr.md)`())`를 포함한 제어된 시퀀스를 기본 술어 정렬로 초기화합니다.  개체 집합`right`에 의해 제어된 시퀀스의 복사본인 초기 제어된 시퀀스를 기본 술어 정렬로 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `template<typename InIter>`  
  
 `set(InIter first, InIter last);`  
  
 시퀀스 `[``first``,` `last``)`를 포함한 제어된 시퀀스를 기본 술어 정렬로 초기화합니다.  기본 술어 정렬을 통해 제어된 시퀀스를 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
 생성자:  
  
 `template<typename InIter>`  
  
 `set(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 시퀀스 `[``first``,` `last``)`를 포함한 제어된 시퀀스를 기본 술어 정렬`pred`로 초기화합니다.  지정된 술어 정렬을 통해 제어된 시퀀스를 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
 생성자:  
  
 `set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 열거자 `right`에 의해 지정된 시퀀스를 포함한 제어된 시퀀스를 기본 술어 정렬로 초기화합니다.  기본 술어 정렬을 통해 제어된 시퀀스를 열거자에 의해 기술된 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
 생성자:  
  
 `set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 열거자 `right`에 의해 지정된 시퀀스를 포함한 제어된 시퀀스를 술어 정렬`pred`로 초기화합니다.  지정된 술어 정렬을 통해 제어된 시퀀스를 열거자에 의해 기술된 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
## 예제  
  
```  
// cliext_set_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
// construct an empty container   
    Myset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **c b a**  
 **a b c**  
 **c b a**  
 **a b c**  
 **c b a**  
 **c b a**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)   
 [set::generic\_container](../dotnet/set-generic-container-stl-clr.md)   
 [set::operator\=](../dotnet/set-operator-assign-stl-clr.md)