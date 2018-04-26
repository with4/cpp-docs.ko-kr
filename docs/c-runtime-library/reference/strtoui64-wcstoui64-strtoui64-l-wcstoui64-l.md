---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d596f66bd3272449466a080cf3ecd2f58fdd8627
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l

서명 되지 않은 문자열 변환 **__int64** 값입니다.

## <a name="syntax"></a>구문

```C
unsigned __int64 _strtoui64(
   const char *strSource,
   char **endptr,
   int base
);
unsigned __int64 _wcstoui64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned __int64 _strtoui64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned __int64 _wcstoui64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
변환할 Null 종료 문자열입니다.

*endptr*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*base*<br/>
사용할 기수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_strtoui64** 문자열에 표시 된 값을 반환 *strSource*표현 하면 오버플로가 발생할 것 때 않는 경우 반환 점을 제외 하 고, **_UI64_MAX**합니다. **_strtoui64** 변환 작업 없이 수행할 수 있으면 0을 반환 합니다.

**_UI64_MAX** 제한에 정의 되어 있습니다. 8.

경우 *strSource* 은 **NULL** 또는 *기본* 0 및 2 되거나 36 보다 큰 **errno** 로 설정 된 **EINVAL** .

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**_strtoui64** 변환 함수 *strSource* 에 **서명 되지 않은** **__int64**합니다. **_wcstoui64** 의 와이드 문자 버전이 **_strtoui64**; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

두 함수는 문자열 읽기 중지 *strSource* 숫자의 일환으로 인식할 수 없습니다 첫 번째 문자에서 합니다. Null 종결 문자 수 또는 것이 보다 크거나 같은 경우 첫 번째 숫자 문자 *기본*합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoui64**|**_strtoui64**|**_strtoui64**|**_wstrtoui64**|
|**_tcstoui64_l**|**_strtoui64_l**|**_strtoui64_l**|**_wstrtoui64_l**|

현재 로캘 **LC_NUMERIC** 범주 설정에는 내의 기 수 문자 인식 여부 결정 *strSource*; 자세한 내용은 참조 [setlocale](setlocale-wsetlocale.md)합니다. 현재 로캘;을 사용 하 여 _l 접미사 없이 함수 **_strtoui64_l** 및 **_wcstoui64_l** 는 동일 하지 않고 해당 함수에는 **_l** 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고 접미사가 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

경우 *endptr* 않습니다 **NULL**, 검색을 중지 하는 문자에 대 한 포인터에서 가리키는 위치에 저장 된 *endptr*합니다. 변환 작업 없이 수행할 수 있으면 (유효 자릿수 없이 발견 된 또는 지정 된 잘못 된 base)의 값 *strSource* 가 가리키는 위치에 저장 된 *endptr*합니다.

**_strtoui64** 예상 *strSource* 다음 형식의 문자열을 가리키도록 합니다.

> [*공백*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*자리* &#124; *문자*]

A *공백* 공백 및 탭 문자가 무시 되는 구성 될 수 있습니다. *자릿수* 는 되는 하나 이상의 10 진수 숫자입니다. *문자* 가 문자 하나 이상의 'a'-'z' (또는 'A'-'Z'). 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. 경우 *기본* 은 2와 36 사이의 수의 기반으로 사용 됩니다. 경우 *기본* 은 0에서 가리키는 문자열의 초기 문자 *strSource* 기본 결정 하는 데 사용 됩니다. 첫 번째 문자가 0이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 *밑*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 경우 *기본* 0의 검색 된 첫 번째 문자는 '0', 8 진수 정수 가정 및 '8' 또는 '9' 문자는 검사를 중지 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_strtoui64**|\<stdlib.h>|
|**_wcstoui64**|\<stdlib.h> 또는 \<wchar.h>|
|**_strtoui64_l**|\<stdlib.h>|
|**_wcstoui64_l**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
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

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
