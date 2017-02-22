---
title: "컴파일러 경고(수준 4) C4703 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4703"
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고(수준 4) C4703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잠재적으로 초기화 되지 않은 지역 포인터 변수 'name'사용.  
  
 지역 포인터 변수 *name* 값을 할당 하지 않고 사용 되었습니다.  이 경우 예측할 수 없는 결과가 발생할 수 있습니다.  
  
## 예제  
 다음 코드에서는 C4701과 C4703 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
  **c:\\src\\test.cpp\(10\): C4701 경고: 'p'가 사용 하는 잠재적으로 초기화 되지 않은 지역 변수**  
 **c:\\src\\test.cpp\(10\): C4703 경고: 'p'가 사용 하는 잠재적으로 초기화 되지 않은 지역 변수** 이 경고를 해결하려면 다음 예제와 같이 변수를 초기화합니다.  
  
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
  
## 참고 항목  
 [컴파일러 경고\(수준 4\) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)   
 [경고, \/sdl, 및 초기화 되지 않은 변수 검색 개선](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)