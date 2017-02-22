---
title: "hash_multiset::hash_multiset(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::hash_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_multiset 멤버[STL/CLR]"
ms.assetid: 1b224c60-b714-4ed5-9234-79b61b92a953
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::hash_multiset(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 개체를 만듭니다.  
  
## 구문  
  
```  
hash_multiset();  
explicit hash_multiset(key_compare^ pred);  
hash_multiset(key_compare^ pred, hasher^ hashfn);  
hash_multiset(hash_multiset<Key>% right);  
hash_multiset(hash_multiset<Key>^ right);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### 매개 변수  
 first  
 삽입할 범위의 시작입니다.  
  
 hashfn  
 버핏에 대한 매핑키를 위한 해시 함수입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 pred  
 제어된 시퀀스를 위한 술부의 정렬입니다.  
  
 right  
 삽입할 범위 또는 개체입니다.  
  
## 설명  
 생성자:  
  
 `hash_multiset();`  
  
 요소가 없고, 기본 순서는 `key_compare()`을 사용하고, 기본 해시함수를 이용하는 제어되는 시퀀스를 초기화합니다.  빈 초기 제어된 시퀀스를 기본 술어 정렬과 해시 함수와 함께 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `explicit hash_multiset(key_compare^ pred);`  
  
 요소가 없고, 순서는 `'pred`을 사용하고, 기본 해시함수를 이용하는 제어되는 순서를 초기화합니다.  빈 초기 제어된 시퀀스를 지정된 술어 정렬과 기본 해시 함수와 함께 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `hash_multiset(key_compare^ pred, hasher^ hashfn);`  
  
 요소가 없고, 순서는 `'pred`을 사용하고, 해시함수 `hashfn`를 이용하는 제어되는 순서를 초기화합니다.  빈 초기 제어된 시퀀스를 지정된 술어 정렬과 해시 함수와 함께 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `hash_multiset(hash_multiset<Key>% right);`  
  
 순서 `[``right``.`[hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)`(),` `right``.`[hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`())` 와 기본 순서를 사용하며 기본 해시함수를 사용하는 제어된 시퀀스를 초기화합니다.  해시 다중집합 개체 `right`에 의해 제어된 시퀀스의 복사본인 초기 제어된 시퀀스를 기본 술어 정렬과 해시함수를 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `hash_multiset(hash_multiset<Key>^ right);`  
  
 순서 `[``right``->`[hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)`(),` `right``->`[hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`())` 와 기본 술어 정렬과 기본 해시함수를 사용하는 제어된 시퀀스를 초기화합니다.  해시 다중집합 개체 `right`에 의해 제어된 시퀀스의 복사본인 초기 제어된 시퀀스를 기본 술어 정렬과 해시함수를 지정하기 위해 사용할 수 있습니다.  
  
 생성자:  
  
 `template<typename InIter>`  
  
 `hash_multiset(InIter first, InIter last);`  
  
 순서 `[``first``,` `last``)` 순서를 사용하고, 기본 술어 정렬과 기본 해시 함수를 사용하는 제어된 시퀀스를 초기화합니다.  기본 술어 정렬과 해시함수를 사용하여 다른 시퀀스의 제어된 시퀀스 복사본을 만드는데 사용합니다..  
  
 생성자:  
  
 `template<typename InIter>`  
  
 `hash_multiset(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 시퀀스 `[``first``,` `last``)`와, `pred`술어 정렬과 기본 해시함수를 사용하여 제어된 시퀀스를 초기화합니다.  명시된 술어 정렬과 기본 해시함수를 사용하여 다른 시퀀스의 제어된 시퀀스 복사본을 만드는데 사용합니다..  
  
 생성자:  
  
 `template<typename InIter>`  
  
 `hash_multiset(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 시퀀스 `[``first``,` `last``)`와, `pred`술어 정렬과 기본 해시함수 `hashfn`를 사용하여 제어된 시퀀스를 초기화합니다.  명시된 술어 정렬과 해시함수를 사용하여 다른 시퀀스의 제어된 시퀀스 복사본을 만드는데 사용합니다..  
  
 생성자:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 열거자 `right` 에 의해 지정된 시퀀스와 기본 술어 정렬, 기본 해시함수를 사용하여 제어된 시퀀스를 초기화합니다.  기본 술어 정렬과 해시함수를 통해 제어된 시퀀스를 열거자에 의해 기술된 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
 생성자:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 열거자 `right` 에 의해 지정된 시퀀스와 술어 정렬 `pred`, 기본 해시함수를 사용하여 제어된 시퀀스를 초기화합니다.  명시된 술어 정렬과 기본 해시함수를 통해 제어된 시퀀스를 열거자에 의해 기술된 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
 생성자:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 열거자 `right` 에 의해 지정된 시퀀스와 술어 정렬 `pred`, 기본 해시함수 `hashfn`를 사용하여 제어된 시퀀스를 초기화합니다.  명시된 술어 정렬과 해시함수를 통해 제어된 시퀀스를 열거자에 의해 기술된 다른 시퀀스의 복사본으로 만들기 위해 사용합니다.  
  
## 예제  
  
```  
// cliext_hash_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
// construct an empty container   
    Myhash_multiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multiset c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multiset c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multiset c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_multiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **a b c**  
**size\(\) \= 0**  
 **c b a**  
 **a b c**  
 **a b c**  
 **c b a**  
 **a b c**  
 **a b c**  
 **c b a**  
 **a b c**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::generic\_container](../dotnet/hash-multiset-generic-container-stl-clr.md)   
 [hash\_multiset::operator\=](../dotnet/hash-multiset-operator-assign-stl-clr.md)