---
title: 기본 형식 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
dev_langs:
- C++
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c24ee360f1c14aa9b355f45ec1c12877efa306c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fundamental-types--c"></a>기본 형식 (C++)
C++의 기본 형식은 정수 계열, 부동 소수점 및 void의 세 가지 범주로 구분됩니다. 정수 계열 형식은 정수를 처리할 수 있습니다. 부동 소수점 형식은 소수 부분이 있을 수 있는 값을 지정할 수 있습니다.  
  
 [void](../cpp/void-cpp.md) 형식은 빈 값 집합을 설명합니다. `void` 형식의 변수를 지정할 수는 없습니다. 이 형식은 값을 반환하지 않는 함수를 선언하거나 형식화되지 않은 데이터 또는 임의로 형식화된 데이터에 대한 제네릭 포인터를 선언하는 데 주로 사용됩니다. 모든 식은 `void`형식으로 명시적으로 변환되거나 캐스팅될 수 있습니다. 그러나 이러한 식은 사용이 다음으로 제한됩니다.  
  
-   식 문. 자세한 내용은 [식](../cpp/expressions-cpp.md)을 참조하세요.  
  
-   쉼표 연산자의 왼쪽 피연산자. 자세한 내용은 [쉼표 연산자](../cpp/comma-operator.md) 를 참조하세요.  
  
-   조건부 연산자의 두 번째 또는 세 번째 피연산자 (`? :`). 자세한 내용은 [조건 연산자를 사용하는 식](../cpp/conditional-operator-q.md) 를 참조하세요.  
  
 다음 표에서는 형식 크기에 대한 제한을 설명합니다. 이러한 제한은 Microsoft 구현과 무관합니다.  
  
### <a name="fundamental-types-of-the-c-language"></a>C++ 언어의 기본 형식  
  
|범주|형식|목차|  
|--------------|----------|--------------|  
|정수 계열|`char`|`char` 형식은 일반적으로 기본 실행 문자 집합의 멤버를 포함하는 정수 계열 형식이며, 기본적으로 Microsoft C++에서는 ASCII입니다.<br /><br /> C++ 컴파일러는 `char`, `signed` `char`및 `unsigned` `char` 형식의 변수를 서로 다른 형식으로 처리합니다. /J 컴파일 옵션을 사용하지 않는 한 기본적으로 `char` 형식의 변수가 `int`  `signed` `char` 로 승격됩니다. 이 경우 변수는 `unsigned` `char` 형식으로 처리되어 부호 확장 없이 `int` 로 승격됩니다.|  
||`bool`|`bool` 형식은 `true` 또는 `false`의 두 값 중 하나를 가질 수 있는 정수 계열 형식입니다. 크기는 지정되지 않습니다.|  
||`short`|`short` `int` 형식(또는 단순히 `short`)은 `char`형식의 크기보다 크거나 같고 `int`형식의 크기보다 짧거나 같은 정수 계열 형식입니다.<br /><br /> `short` 형식의 개체를 `signed` `short` 또는 `unsigned short`로 선언할 수 있습니다. `Signed short` 와 `short`는 동의어입니다.|  
||`int`|`int` 형식은 `short` `int`형식의 크기보다 크거나 같고 `long`형식의 크기보다 짧거나 같은 정수 계열 형식입니다.<br /><br /> `int` 형식의 개체를 `signed` `int` 또는 `unsigned` `int`로 선언할 수 있습니다. `Signed` `int` 와 `int`는 동의어입니다.|  
||`__int8`, `__int16`, `__int32`, `__int64`|크기가 지정된 정수 `__int n`입니다. 여기서 `n` 은 정수 변수의 크기(비트)입니다. `__int8`, `__int16`, `__int32` 과 `__int64` 은 Microsoft 전용 키워드입니다. 일부 아키텍처에서 모든 형식을 사용할 수 있습니다. `(__int128` 지원 되지 않습니다.)|  
||`long`|`long` 형식(또는 `long` `int`)은 `int`형식의 크기보다 크거나 같은 정수 계열 형식입니다.<br /><br /> `long` 형식의 개체를 `signed` `long` 또는 `unsigned` `long`로 선언할 수 있습니다. `Signed` `long` 와 `long`는 동의어입니다.|  
||`long` `long`|부호 없는 `long`보다 큽니다.<br /><br /> `long long` 형식의 개체를 `signed` `long long` 또는 `unsigned` `long long`로 선언할 수 있습니다. `signed` `long long` 에 대 한 동의어 `long long`합니다.|  
||`wchar_t`, `__wchar_t`|`wchar_t` 형식의 변수는 와이드 문자 또는 멀티바이트 문자 형식을 지정합니다. 기본적으로 `wchar_t` 는 네이티브 형식이지만, [/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 를 사용하여 `wchar_t` 를 `unsigned short`에 대한 typedef로 만들 수 있습니다. `__wchar_t` 형식은 네이티브 `wchar_t` 형식의 Microsoft 전용 동의어입니다.<br /><br /> 문자 또는 문자열 리터럴 앞에 L 접두사를 사용하여 와이드 문자 형식을 지정합니다.|  
|부동 소수점|`float`|`float` 형식은 가장 작은 부동 소수점 형식입니다.|  
||`double`|`double` 형식은 `float`형식보다 크거나 같지만 `long` `double`형식의 크기보다 짧거나 같은 부동 소수점 형식입니다.<br /><br /> Microsoft 전용: `long double` 과 `double` 의 표현은 동일합니다. 그러나 `long double` 및 `double` 은 별개 형식입니다.|  
||`long double`|`long` `double` 형식은 `double`형식보다 크거나 같은 부동 소수점 형식입니다.|  
  
 **Microsoft 전용**  
  
 다음 표에서는 Microsoft C++의 기본 형식에 필요한 저장소 크기를 나열합니다.  
  
### <a name="sizes-of-fundamental-types"></a>기본 형식의 크기  
  
|형식|크기|  
|----------|----------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1바이트|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2바이트|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4바이트|  
|`double`, `__int64`, `long double`, `long long`|8바이트|  
  
 **Microsoft 전용 종료**  
  
 각 형식의 값 범위에 대한 요약은 [데이터 형식 범위](../cpp/data-type-ranges.md) 를 참조하세요.  
  
 형식 변환에 대한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식 범위](../cpp/data-type-ranges.md)