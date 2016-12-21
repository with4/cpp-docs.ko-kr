---
title: "operator== (multimap)(STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator== 멤버[STL/CLR]"
ms.assetid: 19f22238-7acf-47dc-b95e-310b39f554ad
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator== (multimap)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동등 비교를 위한 목록입니다.  
  
## 구문  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator==(multimap<Key, Mapped>% left,  
        multimap<Key, Mapped>% right);  
```  
  
#### 매개 변수  
 left  
 비교할 왼쪽 컨테이너입니다.  
  
 right  
 비교할 오른쪽 컨테이너입니다.  
  
## 설명  
 만일 시퀀스가 `left` 에 의해 제어되는 경우 연산자 함수는 오직 true를 반환하고 `right` 은 같은 길이와 각 `i`, `left``[i] ==` `right``[i]`의 위치를 가집니다.  두 멀티맵들의 요소에서 요소를 비교할 때 `left` 가 `right` 와 순서가 같은지 여부의 테스트에 사용합니다.  
  
## 예제  
  
```  
// cliext_multimap_operator_eq.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'a', 1));   
    c2.insert(Mymultimap::make_value(L'b', 2));   
    c2.insert(Mymultimap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[d 4\]**  
**\[a b c\] \=\= \[a b c\] 는 참**  
**\[a b c\] \=\= \[a b d\] 는 거짓**   
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [operator\!\= \(multimap\)](../dotnet/operator-inequality-multimap-stl-clr.md)   
 [operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)   
 [operator\>\= \(multimap\)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)   
 [operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)   
 [operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)