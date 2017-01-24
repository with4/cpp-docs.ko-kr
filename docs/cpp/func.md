---
title: "__func__ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__func__"
  - "__func___cpp"
dev_langs: 
  - "C++"
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __func__
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\(C\+\+11\)** 미리 정의된 식별자 \_\_func\_\_는 바깥쪽 함수의 정규화되지 않고 표시되지 않은 이름을 포함하는 문자열로 암시적으로 정의됩니다.  \_\_func\_\_는 C\+\+ 표준에서 위임되며 Microsoft 확장이 아닙니다.  
  
## 구문  
  
```vb  
__func__  
```  
  
## 반환 값  
 함수 이름을 포함하는 문자의 null 종료 const char 배열을 반환합니다.  
  
## 예제  
  
```  
  
#include <string>  
#include <iostream>  
  
namespace Test  
{  
    struct Foo  
    {  
        static void DoSomething(int i, std::string s)  
        {  
           std::cout << __func__ << std::endl; // Output: DoSomething  
        }  
    };  
}  
int main()  
{  
    Test::Foo::DoSomething(42, "Hello");  
  
    return 0;  
}  
  
```  
  
## 요구 사항  
 C\+\+11