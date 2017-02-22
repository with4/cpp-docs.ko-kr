---
title: "데이터 형식 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FLT_MIN"
  - "SHRT_MAX"
  - "CHAR_MIN"
  - "MB_LEN_MAX"
  - "DBL_EPSILON"
  - "SHRT_MIN"
  - "_FLT_RADIX"
  - "FLT_DIG"
  - "FLT_MAX_10_EXP"
  - "FLT_MANT_DIG"
  - "DBL_MAX_EXP"
  - "SCHAR_MIN"
  - "SCHAR_MAX"
  - "DBL_MIN"
  - "FLT_MIN_10_EXP"
  - "_DBL_ROUNDS"
  - "USHRT_MAX"
  - "FLT_MAX_EXP"
  - "LONG_MAX"
  - "DBL_MAX"
  - "DBL_DIG"
  - "FLT_MIN_EXP"
  - "INT_MIN"
  - "DBL_MIN_10_EXP"
  - "CHAR_BIT"
  - "INT_MAX"
  - "ULONG_MAX"
  - "DBL_MIN_EXP"
  - "LONG_MIN"
  - "_FLT_ROUNDS"
  - "DBL_MANT_DIG"
  - "_DBL_RADIX"
  - "CHAR_MAX"
  - "FLT_MAX"
  - "DBL_MAX_10_EXP"
  - "UCHAR_MAX"
  - "FLT_EPSILON"
  - "UINT_MAX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_DBL_RADIX 상수"
  - "_DBL_ROUNDS 상수"
  - "_FLT_RADIX 상수"
  - "_FLT_ROUNDS 상수"
  - "CHAR_BIT 상수"
  - "CHAR_MAX 상수"
  - "CHAR_MIN 상수"
  - "상수[C++], 데이터 형식"
  - "데이터 형식 상수[C++]"
  - "DBL_DIG 상수"
  - "DBL_EPSILON 상수"
  - "DBL_MANT_DIG 상수"
  - "DBL_MAX 상수"
  - "DBL_MAX_10_EXP 상수"
  - "DBL_MAX_EXP 상수"
  - "DBL_MIN 상수"
  - "DBL_MIN_10_EXP 상수"
  - "DBL_MIN_EXP 상수"
  - "DBL_RADIX 상수"
  - "DBL_ROUNDS 상수"
  - "FLT_DIG 상수"
  - "FLT_EPSILON 상수"
  - "FLT_MANT_DIG 상수"
  - "FLT_MAX 상수"
  - "FLT_MAX_10_EXP 상수"
  - "FLT_MAX_EXP 상수"
  - "FLT_MIN 상수"
  - "FLT_MIN_10_EXP 상수"
  - "FLT_MIN_EXP 상수"
  - "FLT_RADIX 상수"
  - "FLT_ROUNDS 상수"
  - "INT_MAX 상수"
  - "INT_MIN 상수"
  - "LONG_MAX 상수"
  - "LONG_MIN 상수"
  - "MB_LEN_MAX 상수"
  - "SCHAR_MAX 상수"
  - "SCHAR_MIN 상수"
  - "SHRT_MAX 상수"
  - "SHRT_MIN 상수"
  - "UCHAR_MAX 상수"
  - "UINT_MAX 상수"
  - "ULONG_MAX 상수"
  - "USHRT_MAX 상수"
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 데이터 형식 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 형식 상수가 정수 데이터 형식들에 대해 허용되는 값의 범위는 구현에 따라 다릅니다.  아래 나열 된 상수는 정수 계열 데이터 형식에 대한 범위를 제공하고 LIMITS.H 에서 정의됩니다.  
  
> [!NOTE]
>  \/J 컴파일러 옵션은 기본 `char` 에서 `unsigned` 로 변경합니다.  
  
|상수|값|의미|  
|--------|-------|--------|  
|**SCHAR\_MAX**|127|최대 부호가 있는 `char` 값|  
|**SCHAR\_MIN**|–128|최소 부호가 있는 `char` 값|  
|**UCHAR\_MAX**|255\(0Xff\)|최대 `unsigned char` 값|  
|**CHAR\_BIT**|8|`char`에서 비트의 숫자|  
|**USHRT\_MAX**|65535\(0xffff\)|최대 **부호 없는 short** 값|  
|**SHRT\_MAX**|32767|최대 부호\(부호가 있는\) **short** 값|  
|**SHRT\_MIN**|–32768|최대 \(부호가 있는\) **short** 값|  
|**UINT\_MAX**|4294967295\(0xffffffff\)|최대 `unsigned int` 값|  
|**ULONG\_MAX**|4294967295\(0xffffffff\)|최대 `unsigned long` 값|  
|**INT\_MAX**|2147483647|최대 \(부호가 있는 \)`int` 값|  
|**INT\_MIN**|–2147483647–1|최소 \(부호가 있는\) `int` 값|  
|**LONG\_MAX**|2147483647|최대 \(부호가 있는\) **long** 값|  
|**LONG\_MIN**|–2147483647–1|최소 \(부호가 있는\) **long** 값|  
|**CHAR\_MAX**|127 \(\/J 옵션이 사용된 경우255\)|최대 `char` 값|  
|**CHAR\_MIN**|\-128 \(\/J 옵션이 사용된 경우 0\)|최소 `char` 값|  
|**MB\_LEN\_MAX**|2|멀티바이트 `char` 에서 바이트의 최대 수|  
|**\_I64\_MAX**|9223372036854775807|최대 \(부호있는\) \_\_**int64** 값|  
|**\_I64\_MIN**|\-9223372036854775807\-1|최소 \(부호있는\) \_\_**int64** 값|  
|**\_UI64\_MAX**|0xffffffffffffffff|최대 \(부호 없는\) \_\_**int64** 값|  
  
 다음 상수들은 **double** 과 **float** 데이터 형식의 다른 특성과 범위를 제공하고, FLOAT.H에서 정의됩니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|**DBL\_DIG**|15|\# 정밀도 10진수|  
|**DBL\_EPSILON**|2.2204460492503131e\-016|10\+**DBL\_EPSILON** \! \= 1.0 에 대한 가장 작은 값|  
|**DBL\_MANT\_DIG**|53|\# 가수의 비트|  
|**DBL\_MAX**|1.7976931348623158e\+308|최대값|  
|**DBL\_MAX\_10\_EXP**|308|최대 10진수의 지수|  
|**DBL\_MAX\_EXP**|1024|최대 2진수 지수|  
|**DBL\_MIN**|2.2250738585072014e\-308|최소 양수 값입니다.|  
|**DBL\_MIN\_10\_EXP**|\(\-307\)|최소 10진수의 지수|  
|**DBL\_MIN\_EXP**|\(–1021\)|최소 2진수 지수|  
|**\_DBL\_RADIX**|2|지수 기수|  
|**\_DBL\_ROUNDS**|1|추가 반올림: 주변|  
|**FLT\_DIG**|6|정확한 10진의 숫자.|  
|**FLT\_EPSILON**|1.192092896e\-07F|1.0\+**FLT\_EPSILON** \! \= 1.0 에 대한 가장 작은 값|  
|**FLT\_MANT\_DIG**|24|기수에서 비트의 수|  
|**FLT\_MAX**|3.402823466e\+38F|최대값|  
|**FLT\_MAX\_10\_EXP**|38|최대 10진수의 지수|  
|**FLT\_MAX\_EXP**|128|최대 2진수 지수|  
|**FLT\_MIN**|1.175494351e\-38F|최소 양수 값입니다.|  
|**FLT\_MIN\_10\_EXP**|\(–37\)|최소 10진수의 지수|  
|**FLT\_MIN\_EXP**|\(–125\)|최소 2진수 지수|  
|**FLT\_RADIX**|2|지수 기수|  
|**FLT\_ROUNDS**|1|추가 반올림: 주변|  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)