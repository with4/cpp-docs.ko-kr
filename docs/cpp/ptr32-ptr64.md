---
title: "__ptr32, __ptr64 | Microsoft Docs"
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
  - "__ptr32_cpp"
  - "__ptr64_cpp"
  - "__ptr32"
  - "__ptr64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ptr32 키워드[C++]"
  - "__ptr64 키워드[C++]"
  - "_ptr32 키워드[C++]"
  - "_ptr64 키워드[C++]"
  - "ptr32 키워드[C++]"
  - "ptr64 키워드[C++]"
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __ptr32, __ptr64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `__ptr32`는 32비트 시스템의 네이티브 포인터를 나타내는 반면 `__ptr64`는 64비트 시스템의 네이티브 포인터를 나타냅니다.  
  
 다음 예제에서는 이러한 포인터 형식 각각을 선언하는 방법을 보여 줍니다.  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 32비트 시스템에서 `__ptr64`로 선언한 포인터는 32비트 포인터로 잘립니다.  64비트 시스템에서 `__ptr32`로 선언한 포인터는 64비트 포인터로 강제 변환됩니다.  
  
> [!NOTE]
>  `__ptr32`와 컴파일링할 때 `__ptr64` 또는 **\/clr:pure**를 사용할 수 없습니다.  그렇지 않으면 `Compiler Error C2472`가 생성됩니다.  
  
## 예제  
 다음 예제에서는 `__ptr32` 및 `__ptr64` 키워드로 포인터를 선언 및 할당하는 방법을 보여 줍니다.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
  **32**  
**64**   
## Microsoft 전용 종료  
  
## 참고 항목  
 [기본 형식](../cpp/fundamental-types-cpp.md)