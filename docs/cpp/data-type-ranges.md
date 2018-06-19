---
title: 데이터 형식 범위 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- float keyword [C++]
- char keyword [C++]
- unsigned long
- __wchar_t keyword [C++]
- unsigned short int [C++]
- enum keyword [C++]
- unsigned char keyword [C++]
- integer data type [C++], data type ranges
- int data type
- data types [C++], ranges
- unsigned int [C++]
- short data type
- short int data
- signed types [C++], data type ranges
- long long keyword [C++]
- long double keyword [C++]
- double data type [C++], data type ranges
- signed short int [C++]
- unsigned short
- sized integer types
- signed int [C++]
- signed long int [C++]
- signed char keyword [C++]
- wchar_t keyword [C++]
- long keyword [C++]
- ranges [C++]
- unsigned types [C++], data type ranges
- floating-point numbers [C++]
- data type ranges
- ranges [C++], data types
- long int keyword [C++]
- unsigned long int [C++]
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04c809249bbe7513e5a1e439ebaf5e4e44a2f758
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418395"
---
# <a name="data-type-ranges"></a>데이터 형식 범위
Visual C++ 32비트 및 64비트 컴파일러는 이 문서의 뒷부분의 표에 나온 형식을 인식합니다.  
  
-   `int` (`unsigned int`)  
  
-   `__int8` (`unsigned __int8`)  
  
-   `__int16` (`unsigned __int16`)  
  
-   `__int32` (`unsigned __int32`)  
  
-   `__int64` (`unsigned __int64`)  
  
-   `short` (`unsigned short`)  
  
-   `long` (`unsigned long`)  
  
-   `long` `long` (`unsigned long long`)  
  
 이름이 두 개의 밑줄(`__`)로 시작하는 경우 데이터 형식은 비표준입니다.  
  
 다음 표에 지정된 범위는 포함-포함입니다.  
  
|형식 이름|바이트|기타 이름|값의 범위|  
|---------------|-----------|-----------------|---------------------|  
|int|4|signed|–2,147,483,648 ~ 2,147,483,647|  
|unsigned int|4|unsigned|0 ~ 4,294,967,295|  
|__int8|1|char|-128 ~ 127|  
|unsigned __int8|1|unsigned char|0 ~ 255|  
|__int16|2|short, short int 및 signed short int|–32,768 ~ 32,767|  
|unsigned __int16|2|unsigned short, unsigned short int|0 ~ 65,535|  
|__int32|4|signed, signed int 및 int|–2,147,483,648 ~ 2,147,483,647|  
|unsigned __int32|4|unsigned, unsigned int|0 ~ 4,294,967,295|  
|__int64|8|long long, signed long long|–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|  
|unsigned __int64|8|unsigned long long|0 ~ 18,446,744,073,709,551,615|  
|bool|1|없음|false 또는 true|  
|char|1|없음|-기본적으로 128에서 127<br /><br /> [/J](../build/reference/j-default-char-type-is-unsigned.md)를 사용하여 컴파일된 경우 0~255|  
|signed char|1|없음|-128 ~ 127|  
|unsigned char|1|없음|0 ~ 255|  
|short|2|short int, signed short int|–32,768 ~ 32,767|  
|unsigned short|2|unsigned short int|0 ~ 65,535|  
|long|4|long int, signed long int|–2,147,483,648 ~ 2,147,483,647|  
|unsigned long|4|unsigned long int|0 ~ 4,294,967,295|  
|long long|8|없음(그러나 __int64와 동일)|–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|  
|unsigned long long|8|없음(그러나 unsigned __int64와 동일)|0 ~ 18,446,744,073,709,551,615|  
|enum|varies|없음| |  
|float|4|없음|3.4E+/-38(7개의 자릿수)|  
|double|8|없음|1.7E+/-308(15개의 자릿수)|  
|long double|double과 동일|없음|double과 동일|  
|wchar_t|2|__wchar_t|0 ~ 65,535|  
  
 `__wchar_t` 변수는 사용 방법에 따라 와이드 문자 형식 또는 멀티바이트 문자 형식을 지정합니다. 문자 또는 문자열 상수 앞에 `L` 접두사를 사용하여 와이드 문자 형식 상수를 지정합니다.  
  
 `signed` 및 `unsigned` 는 `bool`을 제외한 모든 정수 형식에서 사용할 수 있는 한정자입니다. `char`, `signed char`및 `unsigned char` 는 오버로드 및 템플릿과 같은 메커니즘에 사용되는 3가지 고유 형식입니다.  
  
 `int` 및 `unsigned int` 형식의 크기는 4바이트입니다. 그러나 언어 표준에서 구현 전용으로 허용되므로 이식 가능한 코드는 `int` 의 크기에 의존해서는 안 됩니다.  
  
 Visual Studio의 C/C++에서도 크기가 지정된 정수 형식을 지원합니다. 자세한 내용은 [__int8, \__int16, \__int32, \__int64](../cpp/int8-int16-int32-int64.md) 및 [정수 제한](../cpp/integer-limits.md)을 참조하세요.  
  
 각 형식의 크기 제한에 대한 자세한 내용은 [기본 형식](../cpp/fundamental-types-cpp.md)을 참조하세요.  
  
 열거 형식의 범위는 언어 컨텍스트 및 지정된 컴파일러 플래그에 따라 달라집니다. 자세한 내용은 [C 열거형 선언](../c-language/c-enumeration-declarations.md) 및 [열거형](../cpp/enumerations-cpp.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [기본 형식](../cpp/fundamental-types-cpp.md)