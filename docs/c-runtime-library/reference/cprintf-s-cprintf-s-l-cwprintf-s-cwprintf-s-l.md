---
title: _cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _cwprintf_s_l
- _cprintf_s_l
- _cprintf_s
- _cwprintf_s
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
apitype: DLLExport
f1_keywords:
- _cwprintf_s_l
- _cprintf_s
- cwprintf_s
- _cprintf_s_l
- cwprintf_s_l
- cprintf_s_l
- _tcprintf_s
- cprintf_s
- _cwprintf_s
- tcprintf_s
dev_langs:
- C++
helpviewer_keywords:
- tcprintf_s_l function
- _cprintf_s_l function
- _cwprintf_s_l function
- tcprintf_s function
- _tcprintf_s_l function
- _cwprintf_s function
- cwprintf_s function
- _cprintf_s function
- cprintf_s function
- _tcprintf_s function
- cprintf_s_l function
- cwprintf_s_l function
ms.assetid: c28504fe-0d20-4f06-8f97-ee33225922ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2d8a2f5f80b00eef47d09a8d505f31a42a0fab2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="cprintfs-cprintfsl-cwprintfs-cwprintfsl"></a>_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l

형식을 지정하고 콘솔에 출력합니다. 이러한 버전의 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _cprintf_s(
   const char * format [,
   argument] ...
);
int _cprintf_s_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_s(
   const wchar * format [,
   argument] ...
);
int _cwprintf_s_l(
   const wchar * format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>매개 변수

*format*<br/>
형식 컨트롤 문자열입니다.

*argument*<br/>
선택적 매개 변수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

출력된 문자 수입니다.

## <a name="remarks"></a>설명

이러한 함수는 형식 및 일련의 문자 및 값을 콘솔에 직접 인쇄를 사용 하는 **_putch** 함수 (**_putwch** 에 대 한 **_cwprintf_s**)을 출력 문자 수입니다. 각 *인수* (있는 경우)이 변환 되 고 해당 형식 사양에 따라 출력 *형식*합니다. 형태와 기능을 동일한 형식을 갖고는 *형식* 에 대 한 매개 변수는 [printf_s](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) 함수입니다. 와 달리는 **fprintf_s**, **printf_s**, 및 **sprintf_s** 함수도 **_cprintf_s** 나 **_cwprintf_s** 줄 바꿈 문자를 캐리지 리턴-줄 바꿈 (CR-LF) 조합으로 변환 출력 시.

중요 한 차이점은 **_cwprintf_s** Windows NT에서 사용 될 때 유니코드 문자를 표시 합니다. 와 달리 **_cprintf_s**, **_cwprintf_s** 현재 콘솔 로캘을 사용 하 여

있는 이러한 함수 버전은 **_l** 은 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 하는 점을 제외 하 고 접미사는 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요.

안전 하지 않은 버전을 같은 (참조 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)), 이러한 함수는 매개 변수의 유효성을 검사 하 고에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개변수유효성검사](../../c-runtime-library/parameter-validation.md)경우 *형식* 가 null 포인터입니다. 이러한 함수는 형식 문자열 자체도 유효성이 검사된다는 점에서 안전하지 않은 버전과 다릅니다. 알 수 없거나 잘못된 형식의 형식 지정자가 있는 경우 이러한 함수는 잘못된 매개 변수 처리기를 호출합니다. 모든 경우에 실행을 계속 하도록 허용 된 경우 함수는-1을 반환 하 고 설정 **errno** 를 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_s**|**_cprintf_s**|**_cprintf_s**|**_cwprintf_s**|
|**_tcprintf_s_l**|**_cprintf_s_l**|**_cprintf_s_l**|**_cwprintf_s_l**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_cprintf_s**, **_cprintf_s_l**|\<conio.h>|
|**_cwprintf_s**, **_cwprintf_s_l**|\<conio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_cprintf_s.c
// compile with: /c
// This program displays some variables to the console.

#include <conio.h>

int main( void )
{
   int      i = -16, h = 29;
   unsigned u = 62511;
   char     c = 'A';
   char     s[] = "Test";

   /* Note that console output does not translate \n as
    * standard output does. Use \r\n instead.
    */
   _cprintf_s( "%d  %.4x  %u  %c %s\r\n", i, h, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>참고자료

[콘솔 및 포트 I/O](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)<br/>
[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)<br/>
[형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
