---
title: strtoull, _strtoull_l, wcstoull, _wcstoull_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _strtoull_l
- _wcstoull_l
- strtoull
- wcstoull
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
- _wcstoull_l
- _tcstoull
- _tcstoull_l
- wcstoull
- _strtoull_l
- strtoull
dev_langs:
- C++
helpviewer_keywords:
- strtoull function
- _tcstoull_l function
- _tcstoull function
- _wcstoull_l function
- _strtoull_l function
- wcstoull function
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d698d38fc68a0a6eb49181dcacd7430460524bd6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="strtoull-strtoulll-wcstoull-wcstoulll"></a>strtoull, _strtoull_l, wcstoull, _wcstoull_l
문자열을 부호 없는 long long 정수값으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned long long strtoull(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned long long _strtoull_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned long long wcstoull(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned long long _wcstoull_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nptr`  
 변환할 Null 종료 문자열입니다.  
  
 `endptr`  
 검색을 중지하는 문자에 대한 포인터입니다.  
  
 `base`  
 사용할 기수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `strtoull`은 변환된 값(있는 경우)을 반환하거나 오버플로 시에는 `ULLONG_MAX`를 반환합니다. 변환을 수행할 수 없으면 `strtoull`은 0을 반환합니다. `wcstoull`는 `strtoull`와 동일한 값을 반환합니다. 두 함수에서 모두 오버플로 또는 언더플로가 발생하면 `errno`는 `ERANGE`로 설정됩니다.  
  
 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 이러한 각 함수는 입력 문자열 `nptr`을 `unsigned long long` 정수값으로 변환합니다.  
  
 `strtoull`은 숫자의 일부분으로 인식할 수 없는 첫 문자에서 문자열 `nptr` 읽기를 중지합니다. 이 문자는 종료 null 문자일 수도 있고 `base`보다 크거나 같은 첫 번째 숫자 문자일 수도 있습니다. 로캘의 `LC_NUMERIC` 범주 설정에 따라 `nptr`의 기수 문자 인식이 결정됩니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `strtoull` 및 `wcstoull`은 현재 로캘을 사용합니다. `_strtoull_l` 및 `_wcstoull_l`은 전달된 로캘을 대신 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `endptr`이 `NULL`이 아니면 검색을 중지한 문자에 대한 포인터가 `endptr`에서 가리키는 위치에 저장됩니다. 올바른 숫자를 찾을 수 없거나 잘못된 밑을 지정하여 변환을 수행할 수 없는 경우에는 `nptr`의 값이 `endptr`에서 가리키는 위치에 저장됩니다.  
  
 `wcstoull`은 `strtoull`의 와이드 문자 버전이며 해당 `nptr` 인수는 와이드 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoull`|`strtoull`|`strtoull`|`wcstoull`|  
|`_tcstoull_l`|`strtoull_l`|`_strtoull_l`|`_wcstoull_l`|  
  
 `strtoull`에서는 `nptr`이 다음 형식의 문자열을 가리켜야 합니다.  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits` &#124; [`letters`]]  
  
 `whitespace`는 공백과 탭 문자(무시됨)로 구성될 수 있습니다. `digits`는 하나 이상의 10진수이고 `letters`는 'a'~'z' 또는 'A'~'Z' 범위의 문자 하나 이상입니다. 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. `base`는 2와 36 사이인 경우 숫자의 밑으로 사용됩니다. `base`가 0인 경우에는 `nptr`에서 가리키는 문자열의 초기 문자를 사용하여 밑을 결정합니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 `base`보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 `base`가 0인데 처음 검색된 문자가 '0'이면 문자열은 8진수 정수로 간주되며 '8' 또는 '9' 문자가 발견되면 검색은 중지됩니다. `strtoull`에서는 더하기 기호(`+`) 또는 빼기 기호(`-`) 접두사를 사용할 수 있습니다. 선행 빼기 기호는 반환 값이 부정됨을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`strtoull`|\<stdlib.h>|  
|`wcstoull`|\<stdlib.h> 또는 \<wchar.h>|  
|`_strtoull_l`|\<stdlib.h>|  
|`_wcstoull_l`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [strtod](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [strtoll, _strtoll_l, wcstoll, _wcstoll_l](../../c-runtime-library/reference/strtoll-strtoll-l-wcstoll-wcstoll-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)