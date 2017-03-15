---
title: "크기 사양 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr120.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- size
dev_langs:
- C++
helpviewer_keywords:
- printf function, format specification fields
ms.assetid: 525dc5d8-e70a-4797-a6a0-ec504a27355c
caps.latest.revision: 14
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9041b6c8cc2789b275bf7a62c73102812e5c9c48
ms.lasthandoff: 02/24/2017

---
# <a name="size-specification"></a>크기 사양
서식 사양에서 네 번째 필드는 변환 지정자에 대한 인수 길이 한정자입니다. `type` 필드에 대한 `size` 필드 접두사 `h`, `l`, `w`, `I`, `I32`, `I64` 및 `ll`는 수정되는 변환 지정자에 따라 긴 인수 또는 짧은 인수, 32비트 또는 64비트, 단일 바이트 문자 또는 와이드 문자로 해당 인수의 "크기"를 지정합니다. 아래 표에 표시된 것처럼 이러한 크기 접두사는 `printf` 및 `wprintf` 함수에 `type` 문자와 함께 사용되어 인수 길이 해석을 지정합니다. 일부 인수 형식의 경우 `size` 필드는 선택 사항입니다. 
크기 접두사가 지정되지 않으면 포맷터가 정수 인수(예: 부호 있는 또는 부호 없는 `char`, `short`, `int`, `long` 및 열거형 형식)를 32비트 `int` 형식으로 사용하고 부동 소수점 인수를 64비트 `double` 형식으로 사용합니다. 가변 인수 목록의 기본 인수 승격 규칙과 일치합니다. 인수 승격에 대한 자세한 내용은 [후위 식](../cpp/postfix-expressions.md)의 줄임표 및 기본 인수를 참조하세요. 32비트 및 64비트 시스템 모두에서 `ll` 또는 `I64` 크기 접두사가 64비트 정수 인수의 서식 사양에 포함되어야 합니다. 그렇지 않으면 포맷터 동작이 정의되지 않습니다.  
  
 일부 형식은 32비트 및 64비트 코드에서 크기가 다릅니다. 예를 들어 `size_t`는 x86용으로 컴파일된 코드에서는 32비트 길이이며 x64용으로 컴파일된 코드에서는 64비트입니다. 가변 너비 형식에 대해 플랫폼 제약 없는 서식 코드를 만들려면 가변 너비 인수 길이 한정자를 사용할 수 있습니다. 또는 64비트 인수 길이 한정자를 사용하여 명시적으로 가변 너비 인수 형식을 64비트로 승격합니다. Microsoft 전용 `I` 인수 길이 한정자가 가변 너비 정수 인수를 처리합니다.  
  
> [!NOTE]
>  `I`, `I32`, 및 `I64` 길이 한정자 접두사는 Microsoft 확장이며 ANSI와 호환되지 않습니다. `char` 형식의 데이터와 함께 사용되는 `h` 접두사, `wchar_t` 형식의 데이터와 함께 사용되는 `w` 접두사, `double` 형식의 데이터와 함께 사용되는 `l` 접두사는 Microsoft 확장입니다. `hh`, `j`, `z` 및 `t` 길이 접두사는 지원되지 않습니다.  
  
### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>Printf 및 wprintf 서식 형식 지정자에 대한 크기 접두사  
  
|지정할 함수|접두사 사용|형식 지정자 사용|  
|----------------|----------------|-------------------------|  
|`long int`|`l` (소문자 L)|`d`, `i`, `o`, `x` 또는 `X`|  
|`long unsigned int`|`l`|`o`, `u`, `x` 또는 `X`|  
|`long long`|`ll`|`d`, `i`, `o`, `x` 또는 `X`|  
|`short int`|`h`|`d`, `i`, `o`, `x` 또는 `X`|  
|`short unsigned int`|`h`|`o`, `u`, `x` 또는 `X`|  
|`__int32`|`I32`|`d`, `i`, `o`, `x` 또는 `X`|  
|`unsigned __int32`|`I32`|`o`, `u`, `x` 또는 `X`|  
|`__int64`|`I64`|`d`, `i`, `o`, `x` 또는 `X`|  
|`unsigned __int64`|`I64`|`o`, `u`, `x` 또는 `X`|  
|`ptrdiff_t`(즉, 32비트 플랫폼에서 `__int32`, 64비트 플랫폼에서 `__int64`)|`I`|`d`, `i`, `o`, `x` 또는 `X`|  
|`size_t`(즉, 32비트 플랫폼에서 `unsigned __int32`, 64비트 플랫폼에서 `unsigned __int64`)|`I`|`o`, `u`, `x` 또는 `X`|  
|`long double`([!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]에서는 `long double`이 고유한 형식이나 내부 표현이 `double`과 동일합니다.)|`l` 또는 `L`|`a`, `A`, `e`, `E`, `f`, `g` 또는 `G`|  
|`printf` 및 `wprintf` 함수가 사용되는 단일 바이트 문자입니다. `hc` 또는 `hC` 형식 지정자는 `printf` 함수의 `c` 및 `wprintf` 함수의 `C`와 같습니다.|`h`|`c` 또는 `C`|  
|`printf` 및 `wprintf` 함수가 사용되는 와이드 문자입니다. `lc`, `lC`, `wc` 또는 `wC` 형식 지정자는 `printf` 함수의 `C` 및 `wprintf` 함수의 `c`와 같습니다.|`l` 또는 `w`|`c` 또는 `C`|  
|`printf` 및 `wprintf` 함수가 사용되는 단일 바이트 문자열입니다. `hs` 또는 `hS` 형식 지정자는 `printf` 함수의 `s` 및 `wprintf` 함수의 `S`와 같습니다.|`h`|`s`, `S` 또는 `Z`|  
|`printf` 및 `wprintf` 함수가 사용되는 와이드 문자열입니다. `ls`, `lS`, `ws` 또는 `wS` 형식 지정자는 `printf` 함수의 `S` 및 `wprintf` 함수의 `s`와 같습니다.|`l` 또는 `w`|`s`, `S` 또는 `Z`|  
  
## <a name="see-also"></a>참고 항목  
 [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [플래그 지시문](../c-runtime-library/flag-directives.md)   
 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)   
 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)   
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)
