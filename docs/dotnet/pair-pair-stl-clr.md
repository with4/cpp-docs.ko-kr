---
title: "pair::pair(STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair 멤버[STL/CLR]"
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::pair(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

페어 개체를 생성합니다.  
  
## 구문  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### 매개 변수  
 right  
 스토어에 페어합니다.  
  
 val1  
 스토어의 첫번째 값.  
  
 val2  
 스토어의 두번째값입니다.  
  
## 설명  
 생성자:  
  
 `pair();`  
  
 기본 구성된 값과 저장된 페어를 초기화합니다.  
  
 생성자:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 스토어된 페어를 `right``.`[pair::first](../dotnet/pair-first-stl-clr.md) 와 `right``.`[pair::second](../dotnet/pair-second-stl-clr.md)와 함께 초기화합니다.  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 스토어된 페어를 `right``->`[pair::first](../dotnet/pair-first-stl-clr.md) 와 `right``>`[pair::second](../dotnet/pair-second-stl-clr.md)와 함께 초기화합니다.  
  
 생성자:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 스토어된 페어를 `val1` 및 `val2`과 초기화합니다.  
  
## 예제  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
  **\[\\0, 0\]**  
**\[x, 3\]**  
**\[x, 3\]**  
**\[x, 3\]**   
## 요구 사항  
 **Header:** \<cliext\/utility\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [pair](../dotnet/pair-stl-clr.md)