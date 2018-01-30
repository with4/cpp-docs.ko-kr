---
title: "정수 제한 | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5fc79f225d340777751ca513c0fb47dd33e17ad
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="integer-limits"></a>정수 제한

**Microsoft 전용**

다음 표에서는 정수 형식에 대한 제한 사항을 보여 줍니다. 이러한 제한은 표준 헤더 < limits.h > 파일에도 정의 됩니다.

## <a name="limits-on-integer-constants"></a>정수 상수에 대한 제한

|상수|의미|값|
|--------------|-------------|-----------|
|**CHAR_BIT**|비트 필드가 없는 가장 작은 변수의 비트 수입니다.|9|
|**SCHAR_MIN**|**signed char** 형식 변수의 최소값입니다.|-128|
|**SCHAR_MAX**|**signed char** 형식 변수의 최대값입니다.|127|
|**UCHAR_MAX**|형식 변수의 최대 값 **unsigned char**합니다.|255(0Xff)|
|**CHAR_MIN**|형식의 변수에 대 한 최소 값 **char**합니다.|–128, /J 옵션이 사용된 경우 0|
|**CHAR_MAX**|형식 변수의 최대 값 **char**합니다.|127, /J 옵션이 사용된 경우, 255|
|**MB_LEN_MAX**|여러 문자 상수에서의 최대 바이트 수입니다.|5|
|**SHRT_MIN**|**short** 형식 변수의 최소값입니다.|-32768|
|**SHRT_MAX**|**short** 형식 변수의 최대값입니다.|32767|
|**USHRT_MAX**|**unsigned short** 형식 변수의 최대값입니다.|65535(0xffff)|
|**INT_MIN**|형식의 변수에 대 한 최소 값 **int**합니다.|-2147483648|
|**INT_MAX**|형식 변수의 최대 값 **int**합니다.|2147483647|
|**UINT_MAX**|형식 변수의 최대 값 **부호 없는 int**합니다.|4294967295(0xffffffff)|
|**LONG_MIN**|**long** 형식 변수의 최소값입니다.|-2147483648|
|**LONG_MAX**|**long** 형식 변수의 최대값입니다.|2147483647|
|**ULONG_MAX**|형식 변수의 최대 값 **부호 없는 long**합니다.|4294967295(0xffffffff)|
|**LLONG_MIN**|형식의 변수에 대 한 최소 값 **long long**|-9223372036854775808|
|**LLONG_MAX**|형식 변수의 최대 값 **long long**|9223372036854775807|
|**ULLONG_MAX**|형식 변수의 최대 값 **부호 없는 long long**|18446744073709551615(0xffffffffffffffff)|

값이 최대 정수 표현을 초과하는 경우 Microsoft 컴파일러에서 오류가 발생합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[부동 한계](../cpp/floating-limits.md)  
