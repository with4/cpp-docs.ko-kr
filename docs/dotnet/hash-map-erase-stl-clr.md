---
title: "hash_map::erase(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase 멤버[STL/CLR]"
ms.assetid: 1d2a79aa-62f7-461c-8f7c-7b660eb189be
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_map::erase(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 위치에 있는 요소를 제거합니다.  
  
## 구문  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### 매개 변수  
 first  
 지울 범위의 시작 부분입니다.  
  
 key  
 지울 키 값입니다.  
  
 last  
 지울 범위의 끝입니다.  
  
 where  
 지울 요소입니다.  
  
## 설명  
 첫 번째 멤버 함수는 `where` 가 가르키는 제어되는 시퀀스의 요소를 제거하고 이러한 요소가 없는 경우, 제거 된 요소 다음에 남은 첫 번째 요소를 지정 하는 반복기를 반환하거나 [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()` 를 반환합니다.  단일 요소를 제거 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 `[``first``,` `last``)` 범위에서 제어 되는 시퀀스의 요소를 제거하고 이러한 요소가 존재하지 않는 경우, 제거 된 요소 다음에 남은 첫 번째 요소를 지정하는 반복기 또는 `end()` 를 반환합니다.  0개 이상의 연속 된 요소를 제거 하려면 사용 합니다.  
  
 세 번째 멤버 함수는 키가 `key` 과 같은 제어 되는 시퀀스의 모든 요소를 제거하고 제거된 요소의 수의 개수를 반환합니다.  사용하여 제거하고 지정된 키와 일치하는 모든 요소를 계산합니다.  
  
 각 요소는 제어 되는 시퀀스의 요소 수의 로그에 비례하는 걸린 시간을 제거합니다.  
  
## 예제  
  
```  
// cliext_hash_map_erase.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    cliext::hash_map<wchar_t, int> c1;   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::hash_map<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::hash_map<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::hash_map<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
**erase\(begin\(\)\) \= \[b 2\]**  
 **\[b 2\] \[c 3\] \[d 4\] \[e 5\]**  
**erase\(begin\(\), end\(\)\-1\) \= \[e 5\]**  
**size\(\) \= 1**  
**erase\(L'x'\) \= 0**  
**erase\(L'e'\) \= 1**   
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::clear](../dotnet/hash-map-clear-stl-clr.md)