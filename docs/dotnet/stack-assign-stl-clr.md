---
title: "stack::assign(STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assign 멤버[STL/CLR]"
ms.assetid: 18cc35ad-23cf-4a5a-adae-d967dc5d6980
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::assign(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 요소를 바꿉니다.  
  
## 구문  
  
```  
void assign(stack<Value, Container>% right);  
```  
  
#### 매개 변수  
 right  
 삽입할 컨테이너 어댑터입니다.  
  
## 설명  
 멤버 함수는 내부 컨테이너에 대한 `right``.get_container()` 을 할당합니다.  스택의 전체 내용을 변경하기위해 이것을 사용합니다.  
  
## 예제  
  
```  
// cliext_stack_assign.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mystack c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## 요구 사항  
 **Header:** \<cliext\/stack\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [stack](../dotnet/stack-stl-clr.md)   
 [stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)