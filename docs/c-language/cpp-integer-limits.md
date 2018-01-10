---
title: "C++ 정수 제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 861310be7e13c0ca5e656edc4214e59f5dacd659
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-integer-limits"></a>C++ 정수 제한
**Microsoft 전용**  
  
 다음 표에서는 정수 형식에 대한 제한 사항을 보여 줍니다. 이 제한 사항은 표준 헤더 파일 LIMITS.H에도 정의되어 있습니다. Microsoft C에서는 정수 변수를 8비트, 16비트 또는 32비트의 정수 계열 형식으로 크기를 지정하여 선언할 수 있습니다. 크기가 지정된 정수에 대한 자세한 내용은 [크기 지정 정수 형식](../c-language/c-sized-integer-types.md)을 참조하세요.  
  
### <a name="limits-on-integer-constants"></a>정수 상수에 대한 제한  
  
|**상수**|의미|값|  
|------------------|-------------|-----------|  
|**CHAR_BIT**|비트 필드가 없는 가장 작은 변수의 비트 수입니다.|9|  
|**SCHAR_MIN**|**signed char** 형식 변수의 최소값입니다.|-128|  
|**SCHAR_MAX**|**signed char** 형식 변수의 최대값입니다.|127|  
|**UCHAR_MAX**|`unsigned char` 형식 변수의 최대값입니다.|255(0Xff)|  
|**CHAR_MIN**|`char` 형식 변수의 최소값입니다.|–128, /J 옵션이 사용된 경우 0|  
|**CHAR_MAX**|`char` 형식 변수의 최대값입니다.|127, /J 옵션이 사용된 경우, 255|  
|**MB_LEN_MAX**|여러 문자 상수에서의 최대 바이트 수입니다.|5|  
|**SHRT_MIN**|**short** 형식 변수의 최소값입니다.|-32768|  
|**SHRT_MAX**|**short** 형식 변수의 최대값입니다.|32767|  
|**USHRT_MAX**|**unsigned short** 형식 변수의 최대값입니다.|65535(0xffff)|  
|**INT_MIN**|`int` 형식 변수의 최소값입니다.|-2147483647 - 1|  
|**INT_MAX**|`int` 형식 변수의 최대값입니다.|2147483647|  
|**UINT_MAX**|`unsigned int` 형식 변수의 최대값입니다.|4294967295(0xffffffff)|  
|**LONG_MIN**|**long** 형식 변수의 최소값입니다.|-2147483647 - 1|  
|**LONG_MAX**|**long** 형식 변수의 최대값입니다.|2147483647|  
|**ULONG_MAX**|`unsigned long` 형식 변수의 최대값입니다.|4294967295(0xffffffff)|  
  
 값이 최대 정수 표현을 초과하는 경우 Microsoft 컴파일러에서 오류가 발생합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [C 정수 상수](../c-language/c-integer-constants.md)