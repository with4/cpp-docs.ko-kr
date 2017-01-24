---
title: "컴파일러 경고(수준 4) C4701 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4701"
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초기화되지 않은 'name' 지역 변수를 사용했습니다.  
  
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
 [컴파일러 경고\(수준 4\) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [경고, \/sdl, 및 초기화 되지 않은 변수 검색 개선](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)