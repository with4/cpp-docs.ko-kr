---
title: 컴파일러 오류 C2385 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2385
dev_langs:
- C++
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc152cd9d83b163632e64d1e2d8a0c5692439987
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2385"></a>컴파일러 오류 C2385
'member' 액세스가 모호 합니다  
  
 멤버는 (둘 이상의 개체에서 상속) 둘 이상의 개체에서 파생 될 수 있습니다.  이 오류를 해결 하려면  
  
-   캐스트를 통해 모호 하지 않은 멤버를 확인 합니다.  
  
-   기본 클래스에서 모호한 멤버를 이름을 바꿉니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2385 오류가 발생 합니다.  
  
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