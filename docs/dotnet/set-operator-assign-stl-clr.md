---
title: "set::operator=(STL/CLR) | Microsoft Docs"
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
  - "cliext::set::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 멤버[STL/CLR]"
ms.assetid: 14e16799-d188-4e0d-a0ce-be2c98f93cc8
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set::operator=(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어된 시퀀스를 대체합니다.  
  
## 구문  
  
```  
set<Key>% operator=(set<Key>% right);  
```  
  
#### 매개 변수  
 right  
 복사할 컨테이너입니다.  
  
## 설명  
 멤버 연산자는 개체에 `right`를 복사하고 `*this`를 반환합니다.  제어된 시퀀스를 `right`에서 제어된 시퀀스의 복사본으로 교체하기 위해서 사용합니다.  
  
## 예제  
  
```  
// cliext_set_operator_as.cpp   
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
    for each (Myset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myset c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Myset::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [set](../dotnet/set-stl-clr.md)