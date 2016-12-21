---
title: "기본 형식 (C++) | Microsoft Docs"
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
  - "__wchar_t_cpp"
  - "long_double_cpp"
  - "unsigned"
  - "wchar_t_cpp"
  - "float_cpp"
  - "wchar_t"
  - "char"
  - "char_cpp"
  - "signed"
  - "__wchar_t"
  - "signed_cpp"
  - "short"
  - "double_cpp"
  - "int_cpp"
  - "long"
  - "__intn_cpp"
  - "short_cpp"
  - "double"
  - "unsigned_cpp"
  - "float"
  - "__intn"
  - "long_cpp"
  - "int"
  - "long_double"
  - "unsigned_int"
  - "__int8"
  - "__int8_cpp"
  - "__int16"
  - "__int16_cpp"
  - "__int32"
  - "__int32_cpp"
  - "__int64"
  - "__int64_cpp"
  - "__int128"
  - "__int128_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wchar_t 키워드[C++]"
  - "산술 연산[C++], 형식"
  - "char 키워드[C++]"
  - "데이터 형식[C++], void"
  - "double 데이터 형식, 형식 요약"
  - "float 키워드[C++]"
  - "부동 소수점 숫자, C++ 데이터 형식"
  - "int 데이터 형식"
  - "Integer 데이터 형식, C++ 데이터 형식"
  - "정수 계열 형식"
  - "정수 계열 형식, C++"
  - "long double 키워드[C++]"
  - "long 키워드[C++]"
  - "long 키워드[C++], C++ 데이터 형식"
  - "long long 키워드[C++]"
  - "short 데이터 형식"
  - "부호 있는 형식[C++]"
  - "부호 있는 형식[C++], 데이터 형식 요약"
  - "지정자[C++], 형식"
  - "저장소[C++], basic 형식"
  - "형식 저장[C++]"
  - "형식 지정자[C++]"
  - "부호 없는 형식[C++]"
  - "부호 없는 형식[C++], 데이터 형식 요약"
  - "void 키워드[C++]"
  - "wchar_t 키워드[C++]"
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 기본 형식 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+의 기본 형식은 정수 계열, 부동 소수점 및 void의 세 가지 범주로 구분됩니다. 정수 계열 형식은 정수를 처리할 수 있습니다. 부동 소수점 형식은 소수 부분이 있을 수 있는 값을 지정할 수 있습니다.  
  
 [void](../cpp/void-cpp.md) 형식은 빈 값 집합을 설명합니다.`void` 형식의 변수를 지정할 수는 없습니다. 이 형식은 값을 반환하지 않는 함수를 선언하거나 형식화되지 않은 데이터 또는 임의로 형식화된 데이터에 대한 제네릭 포인터를 선언하는 데 주로 사용됩니다. 모든 식은 `void` 형식으로 명시적으로 변환되거나 캐스팅될 수 있습니다. 그러나 이러한 식은 사용이 다음으로 제한됩니다.  
  
-   식 문. 자세한 내용은 [식](../cpp/expressions-cpp.md)을 참조하세요.  
  
-   쉼표 연산자의 왼쪽 피연산자. 자세한 내용은 [쉼표 연산자](../cpp/comma-operator.md)를 참조하세요.  
  
-   조건 연산자의 두 번째 또는 세 번째 피연산자\(`? :`\)입니다. 자세한 내용은 [조건 연산자를 사용하는 식](../cpp/conditional-operator-q.md)을 참조하세요.  
  
 다음 표에서는 형식 크기에 대한 제한을 설명합니다. 이러한 제한은 Microsoft 구현과 무관합니다.  
  
### C\+\+ 언어의 기본 형식  
  
|범주|형식|목차|  
|--------|--------|--------|  
|정수 계열|`char`|`char` 형식은 일반적으로 기본 실행 문자 집합의 멤버를 포함하는 정수 계열 형식이며, 기본적으로 Microsoft C\+\+에서는 ASCII입니다.<br /><br /> C\+\+ 컴파일러는 `char`, `signed` `char` 및 `unsigned` `char` 형식의 변수를 서로 다른 형식으로 처리합니다. \/J 컴파일 옵션을 사용하지 않는 한 기본적으로 `char` 형식의 변수가 `signed` `char` 형식인 것처럼 `int`로 승격됩니다. 이 경우 변수는 `unsigned` `char` 형식으로 처리되어 부호 확장 없이 `int`로 승격됩니다.|  
||`bool`|`bool` 형식은 `true` 또는 `false`의 두 값 중 하나를 가질 수 있는 정수 계열 형식입니다. 크기는 지정되지 않습니다.|  
||`short`|`short` `int` 형식\(또는 단순히`short`\)은 `char` 형식의 크기보다 크거나 같고 `int` 형식의 크기보다 짧거나 같은 정수 계열 형식입니다.<br /><br /> `short` 형식의 개체를 `signed` `short` 또는 `unsigned short`로 선언할 수 있습니다.`Signed short`와 `short`는 동의어입니다.|  
||`int`|`int` 형식은 `short` `int` 형식의 크기보다 크거나 같고 `long` 형식의 크기보다 짧거나 같은 정수 계열 형식입니다.<br /><br /> `int` 형식의 개체를 `signed` `int` 또는 `unsigned` `int`로 선언할 수 있습니다.`Signed` `int`와 `int`는 동의어입니다.|  
||`__int8`, `__int16`, `__int32`, `__int64`, `__int128`|크기가 지정된 정수 `__int``n`입니다. 여기서 `n`은 정수 변수의 크기\(비트\)입니다.`__int8`, `__int16`, `__int32`, `__int64` 및 `__int128`은 Microsoft 전용 키워드입니다. 일부 형식은 일부 아키텍처에서 사용할 수 없습니다.|  
||`long`|`long` 형식\(또는 `long` `int`\)은 `int` 형식의 크기보다 크거나 같은 정수 계열 형식입니다.<br /><br /> `long` 형식의 개체를 `signed` `long` 또는 `unsigned` `long`로 선언할 수 있습니다.`Signed` `long`와 `long`는 동의어입니다.|  
||`long` `long`|부호 없는 `long`보다 큽니다.<br /><br /> `long long` 형식의 개체를 `signed` `long long` 또는 `unsigned` `long long`로 선언할 수 있습니다.`Signed` `long long`와 `long long`는 동의어입니다.|  
||`wchar_t`, `__wchar_t`|`wchar_t` 형식의 변수는 와이드 문자 또는 멀티바이트 문자 형식을 지정합니다. 기본적으로 `wchar_t`는 네이티브 형식이지만, [\/Zc:wchar\_t\-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 사용하여 `wchar_t`를 `unsigned short`에 대한 typedef로 만들 수 있습니다.`__wchar_t` 형식은 네이티브 `wchar_t` 형식의 Microsoft 전용 동의어입니다.<br /><br /> 문자 또는 문자열 리터럴 앞에 L 접두사를 사용하여 와이드 문자 형식을 지정합니다.|  
|부동 소수점|`float`|`float` 형식은 가장 작은 부동 소수점 형식입니다.|  
||`double`|`double` 형식은 `float` 형식보다 크거나 같지만 `long` `double` 형식의 크기보다 짧거나 같은 부동 소수점 형식입니다.<br /><br /> Microsoft 전용: `long double`과 `double`의 표현은 동일합니다. 그러나 `long double` 및 `double`은 별개 형식입니다.|  
||`long double`|`long` `double` 형식은 `double` 형식보다 크거나 같은 부동 소수점 형식입니다.|  
  
 **Microsoft 전용**  
  
 다음 표에서는 Microsoft C\+\+의 기본 형식에 필요한 저장소 크기를 나열합니다.  
  
### 기본 형식의 크기  
  
|형식|크기|  
|--------|--------|  
|`bool`, `char`, `unsigned char`, `signed char`, `__int8`|1바이트|  
|`__int16`, `short`, `unsigned short`, `wchar_t`, `__wchar_t`|2바이트|  
|`float`, `__int32`, `int`, `unsigned int`, `long`, `unsigned long`|4바이트|  
|`double`, `__int64`, `long double`, `long long`|8바이트|  
|`__int128`|16바이트|  
  
 **Microsoft 전용 종료**  
  
 각 형식의 값 범위에 대한 요약은 [데이터 형식 범위](../cpp/data-type-ranges.md)를 참조하세요.  
  
 형식 변환에 대한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md)을 참조하세요.  
  
## 참고 항목  
 [데이터 형식 범위](../cpp/data-type-ranges.md)