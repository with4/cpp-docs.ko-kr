---
title: "bind1st(STL/CLR) | Microsoft Docs"
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
  - "cliext::bind1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bind1st 함수[STL/CLR]"
ms.assetid: 03a04cef-60fb-4667-b22a-22a387adb028
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bind1st(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`binder1st`  함수 및 인수를 생성합니다.  
  
## 구문  
  
```  
template<typename Fun,  
    typename Arg>  
    binder1st<Fun> bind1st(Fun% functor,  
        Arg left);  
```  
  
## 템플릿 매개 변수  
 Arg  
 인수의 형식입니다.  
  
 Fun  
 함수의 형식입니다.  
  
## 함수 매개 변수  
 함수  
 배치 하는 함수입니다.  
  
 left  
 래핑할 첫 번째 인수입니다.  
  
## 설명  
 템플릿 함수가 반환 [binder1st](../dotnet/binder1st-stl-clr.md)  `<Fun>(functor, left)` 을 반환합니다.  두 번째 인수를 사용 하 여 호출 하는 단일 인수 함수에 인수 두 함수를 첫 번째 인수를 편리 하 게 사용 합니다.  
  
## 예제  
  
```  
// cliext_bind1st.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **\-1 0**  
 **\-1 0**   
## 요구 사항  
 \`**Header:** \<cliext\/functional\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [binder1st](../dotnet/binder1st-stl-clr.md)