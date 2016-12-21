---
title: "__int8, __int16, __int32, __int64 | Microsoft Docs"
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
  - "__int8_cpp"
  - "__int64"
  - "__int8"
  - "__int16"
  - "__int16_cpp"
  - "__int64_cpp"
  - "__int32_cpp"
  - "__int32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__int16 키워드[C++]"
  - "__int32 키워드[C++]"
  - "__int64 키워드[C++]"
  - "__int8 키워드[C++]"
  - "integer 데이터 형식, C++에서의 정수 형식"
  - "정수 형식[C++]"
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __int8, __int16, __int32, __int64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 Microsoft C\/C\+\+는 크기가 지정된 정수 형식을 지원합니다.  **\_\_int***n* 형식 지정자를 사용하여 8, 16, 32 또는 64비트 정수 변수를 선언할 수 있습니다. 여기서 *n*은 8, 16, 32 또는 64입니다.  
  
 다음 예제에서는 이러한 형식의 크기가 지정된 정수 각각에 대해 변수 하나를 선언합니다.  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 `__int8`, `__int16` 및 `__int32` 형식은 동일한 크기를 가진 ANSI 형식에 대한 동의어이고, 여러 플랫폼에서 동일하게 동작하는 이식 가능한 코드 작성에 유용합니다.  `__int8` 데이터 형식은 `char` 형식과 동의어이고, `__int16`은 **short**, 그리고 `__int32`는 `int`와 동의어입니다.  `__int64` 형식에 해당하는 ANSI는 없습니다.  
  
## 예제  
 다음 예제에서는 \_\_int*xx* 매개 변수가 `int`로 승격되는 것을 보여 줍니다.  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
  **func**   
## Microsoft 전용 종료  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [기본 형식](../cpp/fundamental-types-cpp.md)   
 [데이터 형식 범위](../cpp/data-type-ranges.md)