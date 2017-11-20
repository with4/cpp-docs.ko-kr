---
title: "C 부동 소수점 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7bd4bd3e0dc2dcd1388c7e8db5c9fcf209a9b47c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-floating-point-constants"></a>C 부동 소수점 상수
"부동 소수점 상수"는 부호 있는 실수를 나타내는 10진수 숫자입니다. 부호 있는 실수 표현에는 정수 부분, 분수 부분 및 지수가 포함됩니다. 부동 소수점 상수를 사용하여 변경할 수 없는 부동 소수점 값을 나타냅니다.  
  
## <a name="syntax"></a>구문  
 *floating-point-constant*:  
 &nbsp;&nbsp; *fractional-constant exponent-part*<sub>opt</sub> *floating-suffix*<sub>opt</sub>  
 &nbsp;&nbsp; *digit-sequence exponent-part floating-suffix*<sub>opt</sub>  
  
 *fractional-constant*:  
 &nbsp;&nbsp; *digit-sequence*<sub>opt</sub> **.** *digit-sequence*  
 &nbsp;&nbsp; *digit-sequence*  **.**  
  
 *exponent-part*:  
 &nbsp;&nbsp; **e**  *sign*<sub>opt</sub> *digit-sequence*  
 &nbsp;&nbsp; **E**  *sign*<sub>opt</sub> *digit-sequence*  
  
 *sign*: 다음 중 하나  
 &nbsp;&nbsp; **+ -**  
  
 *digit-sequence*:  
 &nbsp;&nbsp; *digit*  
 &nbsp;&nbsp; *digit-sequence digit*  
  
 *floating-suffix*: 다음 중 하나  
 &nbsp;&nbsp; **f l F L**  
  
 소수점 이전 숫자(값의 정수 부분), 소수점 이후 숫자(값의 소수 부분) 중 하나만 생략할 수 있습니다. 지수를 포함하는 경우에만 소수점을 생략할 수 있습니다. 공백 문자로 상수의 숫자나 문자를 구분할 수 없습니다.  
  
 다음 예제에서는 부동 소수점 상수 및 식의 몇 가지 형태를 보여 줍니다.  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 부동 소수점 상수는 빼기 기호(**-**)가 앞에 없는 경우 양수입니다. 이 경우 빼기 기호는 단항 산술 부정 연산자로 처리됩니다. 부동 소수점 상수의 형식은 `float`, `double` 또는 `long double`입니다.  
  
 **f**, **F**, **l** 또는 **L** 접미사가 없는 부동 소수점 상수는 `double` 형식입니다. 문자 **f** 또는 **F**가 접미사이면 상수 형식은 `float`입니다. 그 뒤에 문자 **l** 또는 **L**이 오는 경우 형식은 `long double`입니다. 예:  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Microsoft C 컴파일러는 내부적으로 `long double`을 `double` 형식과 동일하게 나타냅니다. `double`, `float` 및 `long double` 형식에 대한 내용은 [기본 형식 저장소](../c-language/storage-of-basic-types.md)를 참조하세요.  
  
 다음 예제와에서 같이 부동 소수점 상수의 정수 부분을 생략할 수 있습니다. 숫자 .75는 다음을 포함한 다양한 방식으로 나타낼 수 있습니다.  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## <a name="see-also"></a>참고 항목  
 [C 상수](../c-language/c-constants.md)