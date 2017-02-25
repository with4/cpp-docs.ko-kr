---
title: "컴파일러 오류 C2385 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2385"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2385"
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2385
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' 액세스가 모호합니다.  
  
 멤버는 둘 이상의 개체로부터 상속되므로 둘 이상의 개체로부터 파생할 수 있습니다.  이 오류를 해결하려면  
  
-   캐스트를 통해 멤버를 명확하게 만듭니다.  
  
-   기본 클래스에서 모호한 멤버의 이름을 바꿉니다.  
  
## 예제  
 다음 샘플에서는 C2385 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2385.cpp  
// C2385 expected  
#include <stdio.h>  
  
struct A   
{  
    void x(int i)   
    {  
        printf_s("\nIn A::x");  
    }  
};  
  
struct B   
{  
    void x(char c)   
    {  
        printf_s("\nIn B::x");  
    }  
};  
  
// Delete the following line to resolve.  
struct C : A, B {}  
  
// Uncomment the following 4 lines to resolve.  
// struct C : A, B   
// {  
//     using B::x;  
//     using A::x;  
// };  
  
int main()   
{  
    C aC;  
    aC.x(100);  
    aC.x('c');  
}  
  
struct C : A, B   
{  
    using B::x;  
    using A::x;  
};  
```