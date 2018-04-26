---
title: strcmp, wcscmp, _mbscmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9eabb1f7afb860865ecd5526f7577263ccee1e6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp, wcscmp, _mbscmp

비교 문자열입니다.

> [!IMPORTANT]
> **_mbscmp** 는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int strcmp(
   const char *string1,
   const char *string2
);
int wcscmp(
   const wchar_t *string1,
   const wchar_t *string2
);
int _mbscmp(
   const unsigned char *string1,
   const unsigned char *string2
);
```

### <a name="parameters"></a>매개 변수

*string1*, *문자열 2*<br/>
비교할 Null 종료 문자열입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수에 대 한 반환 값의 서 수 관계를 나타냅니다. *string1* 를 *string2*합니다.

|값|문자열 1과 문자열 2의 관계|
|-----------|----------------------------------------|
|< 0|*string1* 는 보다 작은 *문자열 2*|
|0|*string1* 동일 *문자열 2*|
|> 0|*string1* 보다 크면 *문자열 2*|

매개 변수 유효성 검사 오류 시 **_mbscmp** 반환 **_NLSCMPERROR**에 정의 된 \<g. h > 및 \<mbstring.h > 합니다.

## <a name="remarks"></a>설명

**strcmp** 의 서 수 비교를 수행 하는 함수 *string1* 및 *string2* 하 고 서로의 관계를 나타내는 값을 반환 합니다. **wcscmp** 및 **_mbscmp** 는 각각의 와이드 문자 및 멀티 바이트 문자 버전 **strcmp**합니다. **_mbscmp** 현재 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하 고 반환 **_NLSCMPERROR** 오류 발생 시. 자세한 내용은 [코드 페이지](../../c-runtime-library/code-pages.md) 참조하세요. 또한 경우 *string1* 또는 *string2* null 포인터가 **_mbscmp** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개변수유효성검사](../../c-runtime-library/parameter-validation.md). 실행을 계속 하도록 허용 된 경우 **_mbscmp** 반환 **_NLSCMPERROR** 설정 **errno** 를 **EINVAL**합니다. **strcmp** 및 **wcscmp** 매개 변수를 확인 하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscmp**|**strcmp**|**_mbscmp**|**wcscmp**|

**strcmp** 에서 다른는 **strcoll** 함수에는 **strcmp** 비교는 서 수 이며 및 로캘에 의해 영향을 받지 않습니다. **strcoll** 문자열을 사용 하 여 사전순으로 비교는 **LC_COLLATE** 현재 로캘 범주입니다. 에 대 한 자세한 내용은 **LC_COLLATE** 범주 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md)합니다.

"C" 로캘에서 문자 집합(ASCII 문자 집합)의 순서는 사전적 문자 순서와 같습니다. 그러나 다른 로캘에서 문자 집합의 순서는 사전적 순서와 다를 수 있습니다. 예를 들어 특정 유럽 로캘의 문자 집합에서 문자 'a'(값 0x61)는 문자 'ä'(값 0xE4) 앞에 오지만 사전적으로는 문자 'ä'가 'a' 앞에 옵니다.

문자 집합과 사전적 문자 순서가 서로 다른 로캘에서를 사용할 수 있습니다 **strcoll** 대신 **strcmp** 문자열의 사전 순 비교에 대 한 합니다. 사용할 수 있습니다 **strxfrm** 의 원본 문자열에 다음 사용 하 여 **strcmp** 결과 문자열에 있습니다.

**strcmp** 함수는 대/소문자 구분 합니다. **_stricmp**, **_wcsicmp**, 및 **_mbsicmp** 첫 번째을 변환 하 여 소문자 형식 문자열을 비교 합니다. 'Z' 사이 있는 문자가 포함 된 두 문자열와 ASCII 테이블의 ' a' ('[','\\', ']', ' ^', '_' 및 '\`') 소문자에 따라 서로 다른 방식으로 비교 합니다. "ABCDE" 문자열 두는 예를 들어 및 "ABCD ^"은 소문자 경우 ("abcde" > "abcd ^") 및 다른 방법으로 ("ABCDE" < "ABCD ^")가 대문자 비교 하는 경우.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strcmp**|<string.h>|
|**wcscmp**|<string.h> 또는 <wchar.h>|
|**_mbscmp**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_strcmp.c

#include <string.h>
#include <stdio.h>
#include <stdlib.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown dog jumps over the lazy fox";

int main( void )
{
   char tmp[20];
   int result;

   // Case sensitive
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );
   result = strcmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof(tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );

   // Case insensitive (could use equivalent _stricmp)
   result = _stricmp( string1, string2 );
   if( result > 0 )
      strcpy_s( tmp, _countof (tmp), "greater than" );
   else if( result < 0 )
      strcpy_s( tmp, _countof (tmp), "less than" );
   else
      strcpy_s( tmp, _countof (tmp), "equal to" );
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );
}
```

```Output
Compare strings:
   The quick brown dog jumps over the lazy fox
   The QUICK brown dog jumps over the lazy fox

   strcmp:   String 1 is greater than string 2
   _stricmp:  String 1 is equal to string 2
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[_memicmp, _memicmp_l](memicmp-memicmp-l.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
