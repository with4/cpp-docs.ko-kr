---
title: "컴파일러 경고 (수준 4) C4703 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4703
dev_langs: C++
helpviewer_keywords: C4703
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 995491fd4fdd05465b4ebdc961ad7ca09c4e7697
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4703"></a>컴파일러 경고(수준 4) C4703
초기화되지 않았을 수 있는 로컬 포인터 변수 'name'이(가) 사용되었습니다.  
  
 로컬 포인터 변수 *이름* 값을 할당 하지 않고 사용 되었을 수 있습니다. 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 C4701 및 C4703을 생성합니다.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
```Output  
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used  
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used  
  
```  
  
 이 경고를 해결하려면 다음 예제에 표시된 것처럼 변수를 초기화합니다.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 경고 (수준 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)   
 [경고, /sdl 및 초기화 되지 않은 변수 검색 향상](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)