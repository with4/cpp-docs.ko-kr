---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- _wcstoui64_l
- strtoui64_l
- wcstoui64
- _wcstoui64
- _strtoui64_l
- strtoui64
- _strtoui64
- wcstoui64_l
dev_langs: C++
helpviewer_keywords:
- _strtoui64_l function
- _wcstoui64_l function
- string conversion, to integers
- wcstoui64_l function
- _strtoui64 function
- _wcstoui64 function
- wcstoui64 function
- strtoui64_l function
- strtoui64 function
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1c774473bea1449f5ae1b254d1b98abe8a195d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
문자열을 부호 없는 `__int64` 값으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned __int64 _strtoui64(  
   const char *nptr,  
   char **endptr,  
   int base   
);  
unsigned __int64 _wcstoui64(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   int base   
);  
unsigned __int64 _strtoui64_l(  
   const char *nptr,  
   char **endptr,  
   int base,  
   _locale_t locale  
);  
unsigned __int64 _wcstoui64(  
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
 `_strtoui64`는 문자열 `nptr`로 표현되는 값을 반환합니다. 단, 해당 표현으로 인해 오버플로가 발생하는 경우에는 `_UI64_MAX`를 반환합니다. 변환을 수행할 수 없으면 `_strtoui64`은 0을 반환합니다.  
  
 `_UI64_MAX`는 LIMITS.H에서 정의됩니다.  
  
 `nptr`이 `NULL`이거나 `base`가 0이 아니고 2보다 작거나 36보다 크면 `errno`는 `EINVAL`로 설정됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_strtoui64` 변환 함수 `nptr` 에 `unsigned` `__int64`합니다. `_wcstoui64`는 `_strtoui64`의 와이드 문자 버전입니다. 이 함수의 `nptr` 인수는 와이드 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.  
  
 이 두 함수는 숫자의 일부분으로 인식할 수 없는 첫 문자에서 문자열 `nptr` 읽기를 중지합니다. 이 문자는 종료 null 문자일 수도 있고 `base`보다 크거나 같은 첫 번째 숫자 문자일 수도 있습니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstoui64`|`_strtoui64`|`_strtoui64`|`_wstrtoui64`|  
|`_tcstoui64_l`|`_strtoui64_l`|`_strtoui64_l`|`_wstrtoui64_l`|  
  
 현재 로캘의 `LC_NUMERIC` 범주 설정에 따라 `nptr`의 기수 문자 인식이 결정됩니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. 현재 로캘;을 사용 하 여 _l 접미사 없이 함수 `_strtoui64_l` 및 `_wcstoui64_l` 는 동일 하지 않고 해당 함수에는 `_l` 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고 접미사가 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 `endptr`이 `NULL`이 아니면 검색을 중지한 문자에 대한 포인터가 `endptr`에서 가리키는 위치에 저장됩니다. 올바른 숫자를 찾을 수 없거나 잘못된 밑을 지정하여 변환을 수행할 수 없는 경우에는 `nptr`의 값이 `endptr`에서 가리키는 위치에 저장됩니다.  
  
 `_strtoui64`에서는 `nptr`이 다음 형식의 문자열을 가리켜야 합니다.  
  
 [`whitespace`] [{`+` &#124; `-`}] [`0` [{ `x` &#124; `X` }]] [`digits`]  
  
 `whitespace`는 공백 및 탭 문자(무시됨)로 구성될 수 있습니다. `digits`는 하나 이상의 10진수입니다. 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. `base`는 2와 36 사이인 경우 숫자의 밑으로 사용됩니다. `base`가 0인 경우에는 `nptr`에서 가리키는 문자열의 초기 문자를 사용하여 밑을 결정합니다. 첫 번째 문자가 0이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 `base`보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 `base`가 0인데 처음 검색된 문자가 '0'이면 문자열은 8진수 정수로 간주되며 '8' 또는 '9' 문자가 발견되면 검색은 중지됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_strtoui64`|\<stdlib.h>|  
|`_wcstoui64`|\<stdlib.h> 또는 \<wchar.h>|  
|`_strtoui64_l`|\<stdlib.h>|  
|`_wcstoui64_l`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_strtoui64.c  
#include <stdio.h>  
  
unsigned __int64 atoui64(const char *szUnsignedInt) {  
   return _strtoui64(szUnsignedInt, NULL, 10);  
}  
  
int main() {  
   unsigned __int64 u = atoui64("18446744073709551615");  
   printf( "u = %I64u\n", u );  
}  
```  
  
```Output  
u = 18446744073709551615  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, _strtod_l, wcstod, _wcstod_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)