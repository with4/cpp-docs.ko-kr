---
title: "set::erase(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase 멤버[STL/CLR]"
ms.assetid: 0596514b-d4cd-4d2d-8223-3bee6980261c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# set::erase(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 위치에 있는 요소를 제거합니다.  
  
## 구문  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
size_type erase(key_type key)  
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
 첫 번째 멤버 함수는 `where` 가 가르키는 제어되는 시퀀스의 요소를 제거하고 이러한 요소가 없는 경우, 제거 된 요소 다음에 남은 첫 번째 요소를 지정 하는 반복기를 반환하거나 [set::end](../dotnet/set-end-stl-clr.md)`()` 를 반환합니다.  단일 요소를 제거 하려면 사용 합니다.  
  
 두 번째 멤버 함수는 `[``first``,` `last``)` 범위에서 제어 되는 시퀀스의 요소를 제거하고 이러한 요소가 존재하지 않는 경우, 제거 된 요소 다음에 남은 첫 번째 요소를 지정하는 반복기 또는 `end()` 를 반환합니다.  0개 이상의 연속 된 요소를 제거 하려면 사용 합니다.  
  
 세 번째 멤버 함수는 키가 `key` 과 같은 제어 되는 시퀀스의 모든 요소를 제거하고 제거된 요소의 수의 개수를 반환합니다.  사용하여 제거하고 지정된 키와 일치하는 모든 요소를 계산합니다.  
  
 각 요소는 제어 되는 시퀀스의 요소 수의 로그에 비례하는 걸린 시간을 제거합니다.  
  
## 예제  
  
```  
// cliext_set_erase.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Myset::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**erase\(begin\(\)\) \= b**  
 **b c d e**  
**erase\(begin\(\), end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)   
 [set::clear](../dotnet/set-clear-stl-clr.md)