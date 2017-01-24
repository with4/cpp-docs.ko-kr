---
title: "hash_set::insert(STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert 멤버[STL/CLR]"
ms.assetid: 0a9bc9aa-012e-4101-9e8c-f1f4b6b76af7
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::insert(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

요소를 추가합니다.  
  
## 구문  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### 매개 변수  
 first  
 삽입할 범위의 시작입니다.  
  
 last  
 삽입할 범위의 끝입니다.  
  
 right  
 삽입할 열거형입니다.  
  
 val  
 삽입할 키입니다.  
  
 where  
 \(참고만\)삽입할 컨테이너에 위치 합니다.  
  
## 설명  
 각 멤버 함수는 나머지 피연산자에 지정된 시퀀스를 삽입 합니다.  
  
 첫 번째 멤버 함수는 `val` 값에 요소를 삽입합니다. 그리고 `X` 값의 쌍을 반환합니다.  `X.second`가 true이면 `X.first`는 새로 삽입되는 요소를 지정하고, 그렇지 않으면 `X.first`는 이미 있는 요소를 동일한 순서로 지정하며 새 요소가 삽입되지 않습니다.  단일 요소를 삽입 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 `where` 를 힌트로\(성능 향상\) 요소에 `val` 값을 사용하여 삽입하고 새로 삽입된 요소를 지정하는 반복기를 반환합니다.  알고 있는 요소에 인접할 수 있는 단일 요소에 집어넣기 위해 사용합니다.  
  
 세 번째 멤버 함수는 다음 순서로 삽입합니다. `[``first``,` `last``)` 다른 시퀀스에서 복사 된 0 개 이상의 요소를 삽입 하려면 사용 합니다.  
  
 지정 된 시퀀스를 삽입 하는 네 번째 멤버 함수는 `right` 입니다.  열거형에서 설명 하는 순서를 삽입 하려면 사용 합니다.  
  
 각 요소를 삽입은 제어 되는 시퀀스의 요소 수의 로그에 비례 하는 시간입니다.  그러나 삽입은 요소 옆에 삽입 포인터를 지정하는 힌트를 제공하는 상환 일정 시간에서 발생할 수 있습니다.  
  
## 예제  
  
```  
// cliext_hash_set_insert.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
typedef Myhash_set::pair_iter_bool Pairib;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_set c2;   
    Myhash_set::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_set c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**insert\(L'x'\) \= \[x True\]**  
**insert\(L'b'\) \= \[b False\]**  
 **a b c x**  
**insert\(begin\(\), L'y'\) \= y**  
 **a b c x y**  
 **a b c x**  
 **a b c x y**   
## 요구 사항  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_set](../dotnet/hash-set-stl-clr.md)