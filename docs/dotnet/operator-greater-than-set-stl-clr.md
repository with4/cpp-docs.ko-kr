---
title: "operator&gt; (set)(STL/CLR) | Microsoft Docs"
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
  - "cliext::set::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator> 멤버[STL/CLR]"
ms.assetid: 1af7a3bd-011e-4248-902a-f86d4acae856
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt; (set)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

목록은 비교보다 더 큽니다.  
  
## 구문  
  
```  
template<typename Key>  
    bool operator>(set<Key>% left,  
        set<Key>% right);  
```  
  
#### 매개 변수  
 left  
 비교할 왼쪽 컨테이너입니다.  
  
 right  
 비교할 오른쪽 컨테이너입니다.  
  
## 설명  
 연산자 함수는 `right` `<` `left` 을 반환합니다.  두 집합이 요소별로 비교되었을때, `left` 이 `right` 후에 정렬되었는지 여부를 검사하기위해 사용합니다.  
  
## 예제  
  
```  
// cliext_set_operator_gt.cpp   
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
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b d**  
**\[a b c\] \> \[a b c\]는 거짓**  
**\[a b d\] \> \[a b c\] is는 참**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)   
 [operator\=\= \(set\)](../dotnet/operator-equality-set-stl-clr.md)   
 [operator\!\= \(set\)](../dotnet/operator-inequality-set-stl-clr.md)   
 [operator\< \(set\)](../dotnet/operator-less-than-set-stl-clr.md)   
 [operator\>\= \(set\)](../dotnet/operator-greater-or-equal-set-stl-clr.md)   
 [operator\<\= \(set\)](../dotnet/operator-less-or-equal-set-stl-clr.md)