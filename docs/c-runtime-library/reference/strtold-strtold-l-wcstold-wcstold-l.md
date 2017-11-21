---
title: _strtold_l, strtold wcstold, _wcstold_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
dev_langs: C++
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ff8aa3f62a50ae544de61953054bd8906ed5971
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold, _strtold_l, wcstold, _wcstold_l
문자열을 long 배정밀도 부동 소수점 값으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
long double strtold(  
   const char *nptr,  
   char **endptr   
);  
long double _strtold_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
long double wcstold(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
long double wcstold_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nptr`  
 변환할 Null 종료 문자열입니다.  
  
 `endptr`  
 검색을 중지하는 문자에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `strtold`부동 소수점 숫자의 값을 반환는 `long double`, 표현을 오버플로가 인해 경우를 제외 하 고-+ /-함수가 반환 하는 경우`HUGE_VALL`합니다. `HUGE_VALL`의 부호는 표현할 수 없는 값의 부호와 일치합니다. 변환을 수행할 수 없거나 언더플로가 발생하면 `strtold`는 0을 반환합니다.  
  
 `wcstold`는 `strtold`와 동일한 값을 반환합니다. 오버플로나 언더플로가 발생하면 두 함수에 대해 `errno`가 `ERANGE`로 설정되며 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 각 함수는 입력 문자열 `nptr`을 `long double`로 변환합니다. `strtold` 함수는 `nptr`을 long 배정밀도 값으로 변환합니다. `strtold`는 숫자의 일부분으로 인식할 수 없는 첫 문자에서 문자열 `nptr` 읽기를 중지합니다. 이 문자는 종료 null 문자일 수 있습니다. `strtold`의 와이드 문자 버전은 `wcstold`입니다. 이 함수의 `nptr` 인수는 와이드 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstold`|`strtold`|`strtold`|`wcstold`|  
|`_tcstold_l`|`_strtold_l`|`_strtold_l`|`_wcstold_l`|  
  
 현재 로캘의 `LC_NUMERIC` 범주 설정에 따라 `nptr`의 기수 문자 인식이 결정됩니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 함수는 현재 로캘을 사용합니다. `_strtold_l` 및 `_wcstold_l`은 전달된 로캘을 대신 사용한다는 점을 제외하면 `_strtold` 및 `_wcstold`와 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `endptr`이 `NULL`이 아니면 검색을 중지한 문자에 대한 포인터가 `endptr`에서 가리키는 위치에 저장됩니다. 올바른 숫자를 찾을 수 없거나 잘못된 밑을 지정하여 변환을 수행할 수 없는 경우에는 `nptr`의 값이 `endptr`에서 가리키는 위치에 저장됩니다.  
  
 `strtold`에서는 `nptr`이 다음 형식의 문자열을 가리켜야 합니다.  
  
 [`whitespace`] [`sign`] [`digits`] [`.digits`] [ {`d` &#124; `D` &#124; `e` &#124; `E`}[`sign`]`digits`]  
  
 `whitespace`는 공백 및 탭 문자(무시됨)로 구성될 수 있습니다. `sign`은 더하기 기호(`+`) 또는 빼기 기호(`-`)이고 `digits`는 하나 이상의 10진수입니다. 기수 문자 앞에 숫자가 없는 경우 기수 문자 뒤에는 숫자가 하나 이상 있어야 합니다. 10진수 뒤에 지수가 올 수 있습니다. 지수는 소개 문자(`d`, `D`, `e` 또는 `E`) 및 부호 있는 정수(선택 사항)로 구성됩니다. 지수 부분과 기수 문자가 모두 없으면 기수 문자는 문자열의 마지막 숫자를 따르는 것으로 간주합니다. 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`strtold`, `_strtold_l`|\<stdlib.h>|  
|`wcstold`, `_wcstold_l`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_strtold.c  
// Build with: cl /W4 /Tc crt_strtold.c  
// This program uses strtold to convert a  
// string to a long double-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   long double x;  
  
   string = "3.1415926535898This stopped it";  
   x = strtold(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtold = %.13Lf\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
```Output  
string = 3.1415926535898This stopped it  
   strtold = 3.1415926535898  
   Stopped scan at: This stopped it  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)