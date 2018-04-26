---
title: strcpy_s, wcscpy_s _mbscpy_s | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2086
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcscpy_s
- _mbscpy_s
- strcpy_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strcpy_s
- _mbscpy_s
- _tcscpy_s
- wcscpy_s
dev_langs:
- C++
helpviewer_keywords:
- strcpy_s function
- _tcscpy_s function
- _mbscpy_s function
- copying strings
- strings [C++], copying
- tcscpy_s function
- wcscpy_s function
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16dfe0f560097ab7a5a423f7730c215c2d05530f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="strcpys-wcscpys-mbscpys"></a>strcpy_s, wcscpy_s, _mbscpy_s

문자열을 복사합니다. 이러한 버전의 [strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> **_mbscpy_s** 는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t strcpy_s(
   char *dest,
   rsize_t dest_size,
   const char *src
);
errno_t wcscpy_s(
   wchar_t *dest,
   rsize_t dest_size,
   const wchar_t *src
);
errno_t _mbscpy_s(
   unsigned char *dest,
   rsize_t dest_size,
   const unsigned char *src
);
```

```cpp
// Template functions are C++ only:
template <size_t size>
errno_t strcpy_s(
   char (&dest)[size],
   const char *src
); // C++ only
template <size_t size>
errno_t wcscpy_s(
   wchar_t (&dest)[size],
   const wchar_t *src
); // C++ only
template <size_t size>
errno_t _mbscpy_s(
   unsigned char (&dest)[size],
   const unsigned char *src
); // C++ only
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
대상 문자열 버퍼의 위치입니다.

*dest_size*<br/>
대상 문자열 버퍼의 크기 **char** 좁은 문자열과 멀티 바이트 함수에 대 한 단위 및 **wchar_t** 넓은 함수에 대 한 단위입니다. 이 값은 0 보다 크고 보다 크지 않음 이어야 합니다 **RSIZE_MAX**합니다.

*src*<br/>
null 종료 소스 문자열 버퍼입니다.

## <a name="return-value"></a>반환 값

성공하면 0이고, 실패하면 오류입니다.

### <a name="error-conditions"></a>오류 조건

|*dest*|*dest_size*|*src*|반환 값|내용을 *dest*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL**|모두|모두|**EINVAL**|수정 안 됨|
|모두|모두|**NULL**|**EINVAL**|*dest*[0]을 0으로 설정|
|모두|0 또는 너무 작음|모두|**ERANGE**|*dest*[0]을 0으로 설정|

## <a name="remarks"></a>설명

**strcpy_s** 함수의 주소에 내용을 복사 *src*, 지정 된 위치에 종료 null 문자를 포함 하 여 *dest*합니다. 대상 문자열은 소스 문자열 및 이 문자열의 null 종결 문자를 포함할 만큼 충분히 커야 합니다. 동작은 **strcpy_s** 소스 문자열과 대상 문자열이 겹치는 경우 정의 되지 않습니다.

**wcscpy_s** 의 와이드 문자 버전이 **strcpy_s**, 및 **_mbscpy_s** 은 멀티 바이트 문자 버전입니다. 인수 **wcscpy_s** 은 와이드 문자열이 고 **_mbscpy_s** 는 멀티 바이트 문자 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

경우 *dest* 또는 *src* null 포인터가 아니면 대상 문자열 크기가 *dest_size* 에설명된대로용량이부족잘못된매개변수처리기가호출[매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우 이러한 함수가 반환 **EINVAL** 설정 **errno** 를 **EINVAL** 때 *dest* 또는  *src* null 포인터 이며 반환 **ERANGE** 설정 **errno** 를 **ERANGE** 대상 문자열이 너무 작은 경우.

실행이 완료되면 대상 문자열은 항상 null로 종료됩니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없음), 보안 수준이 낮은 기존 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 우선 0xFE로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscpy_s**|**strcpy_s**|**_mbscpy_s**|**wcscpy_s**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strcpy_s**|\<string.h>|
|**wcscpy_s**|\<string.h> 또는 \<wchar.h>|
|**_mbscpy_s**|\<mbstring.h>|

이러한 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

프로덕션 품질의 코드와 달리이 샘플 오류를 확인 하지 않고 보안 문자열 함수를 호출 합니다.

```C
// crt_strcpy_s.c
// Compile by using: cl /W4 crt_strcpy_s.c
// This program uses strcpy_s and strcat_s
// to build a phrase.

#include <string.h>     // for strcpy_s, strcat_s
#include <stdlib.h>     // for _countof
#include <stdio.h>      // for printf
#include <errno.h>      // for return values

int main(void)
{
    char string[80];

    strcpy_s(string, _countof(string), "Hello world from ");
    strcat_s(string, _countof(string), "strcpy_s ");
    strcat_s(string, _countof(string), "and ");
    strcat_s(string, _countof(string), "strcat_s!");

    printf("String = %s\n", string);
}
```

```Output
String = Hello world from strcpy_s and strcat_s!
```

C + + 코드를 작성할 때 템플릿 버전은 사용 하기 쉽게 수 있습니다.

```cpp
// crt_wcscpy_s.cpp
// Compile by using: cl /EHsc /W4 crt_wcscpy_s.cpp
// This program uses wcscpy_s and wcscat_s
// to build a phrase.

#include <cstring>  // for wcscpy_s, wcscat_s
#include <cstdlib>  // for _countof
#include <iostream> // for cout, includes <cstdlib>, <cstring>
#include <errno.h>  // for return values

int main(void)
{
    wchar_t string[80];
    // using template versions of wcscpy_s and wcscat_s:
    wcscpy_s(string, L"Hello world from ");
    wcscat_s(string, L"wcscpy_s ");
    wcscat_s(string, L"and ");
    // of course we can supply the size explicitly if we want to:
    wcscat_s(string, _countof(string), L"wcscat_s!");

    std::wcout << L"String = " << string << std::endl;
}
```

```Output
String = Hello world from wcscpy_s and wcscat_s!
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md) <br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
