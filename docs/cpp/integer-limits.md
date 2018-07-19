---
title: 정수 제한 | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 174025fc1a44ce0db96a5a7038502dfabe90bfd6
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940136"
---
# <a name="integer-limits"></a>정수 제한

**Microsoft 전용**

다음 표에서는 정수 형식에 대한 제한 사항을 보여 줍니다. 이러한 제한은 표준 헤더 파일 < limits.h >에 정의 됩니다.

## <a name="limits-on-integer-constants"></a>정수 상수에 대한 제한

|상수|의미|값|
|--------------|-------------|-----------|
|CHAR_BIT|비트 필드가 없는 가장 작은 변수의 비트 수입니다.|8|
|SCHAR_MIN|**signed char** 형식 변수의 최소값입니다.|-128|
|SCHAR_MAX|**signed char** 형식 변수의 최대값입니다.|127|
|UCHAR_MAX|**unsigned char** 형식 변수의 최대값입니다.|255(0Xff)|
|CHAR_MIN|**char** 형식 변수의 최소값입니다.|–128, /J 옵션이 사용된 경우 0|
|CHAR_MAX|**char** 형식 변수의 최대값입니다.|127, /J 옵션이 사용된 경우, 255|
|MB_LEN_MAX|여러 문자 상수에서의 최대 바이트 수입니다.|5|
|SHRT_MIN|**short** 형식 변수의 최소값입니다.|-32768|
|SHRT_MAX|**short** 형식 변수의 최대값입니다.|32767|
|USHRT_MAX|**unsigned short** 형식 변수의 최대값입니다.|65535(0xffff)|
|INT_MIN|**int** 형식 변수의 최소값입니다.|-2147483648|
|INT_MAX|**int** 형식 변수의 최대값입니다.|2147483647|
|UINT_MAX|**unsigned int** 형식 변수의 최대값입니다.|4294967295(0xffffffff)|
|LONG_MIN|**long** 형식 변수의 최소값입니다.|-2147483648|
|LONG_MAX|**long** 형식 변수의 최대값입니다.|2147483647|
|ULONG_MAX|**unsigned long** 형식 변수의 최대값입니다.|4294967295(0xffffffff)|
|LLONG_MIN|형식 변수의 최소값 **long long**|-9223372036854775808|
|LLONG_MAX|형식 변수의 최대값 **long long**|9223372036854775807|
|ULLONG_MAX|형식 변수의 최대값 **부호 없는 long long**|18446744073709551615(0xffffffffffffffff)|

값이 최대 정수 표현을 초과하는 경우 Microsoft 컴파일러에서 오류가 발생합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[부동 한계](../cpp/floating-limits.md)  
