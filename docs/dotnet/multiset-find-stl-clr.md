---
title: "multiset::find(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find 멤버[STL/CLR]"
ms.assetid: 162c9002-fb34-44f9-8e42-6bacecd0ebbc
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multiset::find(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 키와 일치하는 요소를 찾습니다.  
  
## 구문  
  
```  
iterator find(key_type key);  
```  
  
#### 매개 변수  
 key  
 검색할 키 값입니다.  
  
## 설명  
 만일 제어되는 시퀀스의 적어도 하나의 원소가 `key`를 사용하는 순서와 동일하다면, 멤버 함수는 이들 요소들의 하나를 지정하는 반복기를 반환합니다; 그렇지 않으면 이것은 [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`를 반환합니다.  지정된 키와 일치하는 제어된 시퀀스에서 현재 요소를 위치시키기 위해 이것을 사용합니다.  
  
## 예제  
  
```  
// cliext_multiset_find.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**find A \= False**  
**find b \= b**  
**find C \= False**   
## 설명  
 `find` 는 이것을 찾는 여러 요소를 보증하지 않는 것을 주목하세요.  
  
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset::lower\_bound](../dotnet/multiset-lower-bound-stl-clr.md)   
 [multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)