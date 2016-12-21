---
title: "list::operator=(STL/CLR) | Microsoft Docs"
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
  - "cliext::list::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 멤버[STL/CLR]"
ms.assetid: 0e4fdcc6-7574-40af-b947-98c2c683676d
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::operator=(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어된 시퀀스를 대체합니다.  
  
## 구문  
  
```  
list<Value>% operator=(list<Value>% right);  
```  
  
#### 매개 변수  
 right  
 복사할 컨테이너입니다.  
  
## 설명  
 멤버 연산자는 개체에 `right`를 복사하고 `*this`를 반환합니다.  제어된 시퀀스를 `right`에서 제어된 시퀀스의 복사본으로 교체하기 위해서 사용합니다.  
  
## 예제  
  
```  
// cliext_list_operator_as.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)