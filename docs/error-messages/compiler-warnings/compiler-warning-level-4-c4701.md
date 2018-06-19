---
title: 컴파일러 경고 (수준 4) C4701 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4701
dev_langs:
- C++
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48df2f4ac3d5aad4ae82abf76dab4d96e8af89a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293951"
---
# <a name="compiler-warning-level-4-c4701"></a>컴파일러 경고(수준 4) C4701
'name'가 사용 되는 잠재적으로 초기화 되지 않은 지역 변수  
  
 지역 변수 *이름* 값을 할당 하지 않고 사용 되었을 수 있습니다. 예기치 않은 결과가 발생할 수 있습니다.  
  
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
 [컴파일러 경고 (수준 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [경고, /sdl 및 초기화 되지 않은 변수 검색 향상](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)