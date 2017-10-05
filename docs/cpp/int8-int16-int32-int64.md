---
title: __int8, __int16, __int32, __int64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __int8_cpp
- __int64
- __int8
- __int16
- __int16_cpp
- __int64_cpp
- __int32_cpp
- __int32
dev_langs:
- C++
helpviewer_keywords:
- __int16 keyword [C++]
- integer data type, integer types in C++
- __int32 keyword [C++]
- integer types [C++]
- __int8 keyword [C++]
- __int64 keyword [C++]
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 82b06a776d40121b5f147388dadf053b5b072659
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="int8-int16-int32-int64"></a>__int8, __int16, __int32, __int64
## <a name="microsoft-specific"></a>Microsoft 전용  
 Microsoft C/C++는 크기가 지정된 정수 형식을 지원합니다. 사용 하 여 8, 16, 32 또는 64 비트 정수 변수를 선언할 수 있습니다는 **__int** * n * 형식 지정자, 여기서 * n * 8, 16, 32 또는 64입니다.  
  
 다음 예제에서는 이러한 형식의 크기가 지정된 정수 각각에 대해 변수 하나를 선언합니다.  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 `__int8`, `__int16` 및 `__int32` 형식은 동일한 크기를 가진 ANSI 형식에 대한 동의어이고, 여러 플랫폼에서 동일하게 동작하는 이식 가능한 코드 작성에 유용합니다. `__int8` 데이터 형식이 형식과 동의어 `char`, `__int16` 형식과 동의어 **짧은**, 및 `__int32` 형식과 동의어 `int`합니다. `__int64` 형식에 해당하는 ANSI는 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플은 하 한 __int*xx* 매개 변수로 승격 된다는 `int`:  
  
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
  
```Output  
func  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [기본 형식](../cpp/fundamental-types-cpp.md)   
 [데이터 형식 범위](../cpp/data-type-ranges.md)
