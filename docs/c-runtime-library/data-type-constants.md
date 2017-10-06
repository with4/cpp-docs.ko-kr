---
title: "데이터 형식 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FLT_MIN
- SHRT_MAX
- CHAR_MIN
- MB_LEN_MAX
- DBL_EPSILON
- SHRT_MIN
- _FLT_RADIX
- FLT_DIG
- FLT_MAX_10_EXP
- FLT_MANT_DIG
- DBL_MAX_EXP
- SCHAR_MIN
- SCHAR_MAX
- DBL_MIN
- FLT_MIN_10_EXP
- _DBL_ROUNDS
- USHRT_MAX
- FLT_MAX_EXP
- LONG_MAX
- DBL_MAX
- DBL_DIG
- FLT_MIN_EXP
- INT_MIN
- DBL_MIN_10_EXP
- CHAR_BIT
- INT_MAX
- ULONG_MAX
- DBL_MIN_EXP
- LONG_MIN
- _FLT_ROUNDS
- DBL_MANT_DIG
- _DBL_RADIX
- CHAR_MAX
- FLT_MAX
- DBL_MAX_10_EXP
- UCHAR_MAX
- FLT_EPSILON
- UINT_MAX
dev_langs:
- C++
helpviewer_keywords:
- DBL_MAX_EXP constant
- _DBL_RADIX constant
- FLT_MIN_EXP constant
- DBL_EPSILON constant
- INT_MIN constant
- FLT_EPSILON constant
- DBL_MANT_DIG constant
- _FLT_RADIX constant
- DBL_MIN constant
- USHRT_MAX constant
- FLT_MAX_10_EXP constant
- _FLT_ROUNDS constant
- data type constants [C++]
- _DBL_ROUNDS constant
- CHAR_MAX constant
- FLT_MAX_EXP constant
- FLT_MIN constant
- CHAR_MIN constant
- FLT_MIN_10_EXP constant
- DBL_MIN_EXP constant
- SCHAR_MAX constant
- FLT_RADIX constant
- CHAR_BIT constant
- UCHAR_MAX constant
- DBL_RADIX constant
- FLT_ROUNDS constant
- LONG_MIN constant
- SHRT_MAX constant
- LONG_MAX constant
- DBL_MAX_10_EXP constant
- DBL_MIN_10_EXP constant
- INT_MAX constant
- constants [C++], data type
- ULONG_MAX constant
- FLT_DIG constant
- MB_LEN_MAX constant
- DBL_DIG constant
- SHRT_MIN constant
- DBL_MAX constant
- DBL_ROUNDS constant
- FLT_MAX constant
- UINT_MAX constant
- FLT_MANT_DIG constant
- SCHAR_MIN constant
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 1406e086818ea6f71d32e345aaf3d0d79b91940c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="data-type-constants"></a>데이터 형식 상수
데이터 형식 상수는 정수 데이터 형식에 대해 허용되는 값의 구현에 따라 다른 값입니다. 아래 나열된 상수는 정수 데이터 형식의 범위를 제공하고 LIMITS.H에 정의됩니다.  
  
> [!NOTE]
>  /J 컴파일러 옵션은 기본 `char` 형식을 `unsigned`로 변경합니다.  
  
|상수|값|의미|  
|--------------|-----------|-------------|  
|**SCHAR_MAX**|127|최대 부호 있는 `char` 값|  
|**SCHAR_MIN**|-128|최소 부호 있는 `char` 값|  
|**UCHAR_MAX**|255(0Xff)|최대 `unsigned char` 값|  
|**CHAR_BIT**|9|`char`의 비트 수|  
|**USHRT_MAX**|65535(0xffff)|최대 **unsigned short** 값|  
|**SHRT_MAX**|32767|최대 (부호 있는) **short** 값|  
|**SHRT_MIN**|-32768|최소 (부호 있는) **short** 값|  
|**UINT_MAX**|4294967295(0xffffffff)|최대 `unsigned int` 값|  
|**ULONG_MAX**|4294967295(0xffffffff)|최대 `unsigned long` 값|  
|**INT_MAX**|2147483647|최대 (부호 있는) `int` 값|  
|**INT_MIN**|-2147483647-1|최소 (부호 있는) `int` 값|  
|**LONG_MAX**|2147483647|최대 (부호 있는) **long** 값|  
|**LONG_MIN**|-2147483647-1|최소 (부호 있는) **long** 값|  
|**CHAR_MAX**|127(/J 옵션이 사용된 경우 255)|최대 `char` 값|  
|**CHAR_MIN**|-128(/J 옵션이 사용된 경우 0)|최소 `char` 값|  
|**MB_LEN_MAX**|2|최대 바이트 수(멀티바이트) `char`|  
|**_I64_MAX**|9223372036854775807|최대 (부호 있는) __**int64** 값|  
|**_I64_MIN**|-9223372036854775807-1|최소 (부호 있는) __**int64** 값|  
|**_UI64_MAX**|0xffffffffffffffff|최대 (부호 없는) __**int64** 값|  
  
 다음 상수는 **double** 및 **float** 데이터 형식의 범위와 기타 특성을 제공하며, FLOAT.H에 정의됩니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|**DBL_DIG**|15|전체 자릿수|  
|**DBL_EPSILON**|2.2204460492503131e-016|1.0+**DBL_EPSILON** !=1.0처럼 가장 작은 수|  
|**DBL_MANT_DIG**|53|비트 수(가수)|  
|**DBL_MAX**|1.7976931348623158e+308|최대값|  
|**DBL_MAX_10_EXP**|308|최대 10진수 지수|  
|**DBL_MAX_EXP**|1024|최대 이진 지수|  
|**DBL_MIN**|2.2250738585072014e-308|최소 양수 값|  
|**DBL_MIN_10_EXP**|(-307)|최소 10진수 지수|  
|**DBL_MIN_EXP**|(-1021)|최소 이진 지수|  
|**_DBL_RADIX**|2|지수 기수|  
|**_DBL_ROUNDS**|1|더하기 반올림: 근사값|  
|**FLT_DIG**|6|전체 자릿수|  
|**FLT_EPSILON**|1.192092896e-07F|1.0+**FLT_EPSILON** !=1.0처럼 가장 작은 수|  
|**FLT_MANT_DIG**|24|비트 수(가수)|  
|**FLT_MAX**|3.402823466e+38F|최대값|  
|**FLT_MAX_10_EXP**|38|최대 10진수 지수|  
|**FLT_MAX_EXP**|128|최대 이진 지수|  
|**FLT_MIN**|1.175494351e-38F|최소 양수 값|  
|**FLT_MIN_10_EXP**|(-37)|최소 10진수 지수|  
|**FLT_MIN_EXP**|(-125)|최소 이진 지수|  
|**FLT_RADIX**|2|지수 기수|  
|**FLT_ROUNDS**|1|더하기 반올림: 근사값|  
  
## <a name="see-also"></a>참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)
