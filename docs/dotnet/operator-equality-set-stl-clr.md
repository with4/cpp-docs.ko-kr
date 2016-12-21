---
title: "operator== (set)(STL/CLR) | Microsoft Docs"
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
  - "cliext::set::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator== 멤버[STL/CLR]"
ms.assetid: 013a0a76-11fa-4fde-8a84-d96e26f56774
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator== (set)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동등 비교를 위한 목록입니다.  
  
## 구문  
  
```  
template<typename Key>  
    bool operator==(set<Key>% left,  
        set<Key>% right);  
```  
  
#### 매개 변수  
 left  
 비교할 왼쪽 컨테이너입니다.  
  
 right  
 비교할 오른쪽 컨테이너입니다.  
  
## 설명  
 만일 시퀀스가 `left` 에 의해 제어되는 경우 연산자 함수는 오직 true를 반환하고 `right` 은 같은 길이와 각 `i`, `left``[i] ==` `right``[i]`의 위치를 가집니다.   두 쌍의 요소에서 요소를 비교할 때  `left` 가  `right` 와 순서가 같은지 여부의 테스트에 사용합니다.  
  
## 예제  
  
```  
// cliext_set_operator_eq.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \=\= \[a b c\] 는 참**  
**\[a b c\] \=\= \[a b d\] 는 거짓**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)   
 [operator\!\= \(set\)](../dotnet/operator-inequality-set-stl-clr.md)   
 [operator\< \(set\)](../dotnet/operator-less-than-set-stl-clr.md)   
 [operator\>\= \(set\)](../dotnet/operator-greater-or-equal-set-stl-clr.md)   
 [operator\> \(set\)](../dotnet/operator-greater-than-set-stl-clr.md)   
 [operator\<\= \(set\)](../dotnet/operator-less-or-equal-set-stl-clr.md)