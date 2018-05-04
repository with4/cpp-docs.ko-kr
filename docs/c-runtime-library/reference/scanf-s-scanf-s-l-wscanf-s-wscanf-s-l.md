---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: 33
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96b40d891c4148a92a3d2f0060401cd84b371d73
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l

표준 입력 스트림에서 형식이 지정된 데이터를 읽습니다. 이러한 버전의 [scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
int scanf_s(
   const char *format [,
   argument]...
);
int _scanf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf_s(
   const wchar_t *format [,
   argument]...
);
int _wscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>매개 변수

*format*<br/>
형식 컨트롤 문자열입니다.

*argument*<br/>
선택적 인수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공적으로 변환되고 할당된 필드 수를 반환합니다. 이때 읽혀졌지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다. 반환 값이 0이면 할당된 필드가 없음을 나타냅니다. 반환 값은 **EOF** 는 오류에 대 한 파일의 끝 문자 또는 문자열의 끝 문자 문자를 읽는 첫 번째 시도에서 발생 하는 경우. 경우 *형식* 는 **NULL** 에 설명 된 대로 포인터, 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **scanf_s** 및 **wscanf_s** 반환 **EOF** 설정 **errno** 를 **EINVAL**.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**scanf_s** 함수는 표준 입력 스트림에서 데이터를 읽는 **stdin** 위치를 지정 하 여에 데이터를 기록 하 고 *인수*합니다. 각 *인수* 의 형식 지정자에 해당 하는 형식의 변수에 대 한 포인터 여야 *형식*합니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.

**wscanf_s** 의 와이드 문자 버전이 **scanf_s**; *형식* 인수를 **wscanf_s** 는 와이드 문자 문자열입니다. **wscanf_s** 및 **scanf_s** 스트림이 ANSI 모드에서 열리는 경우 동일 하 게 작동 합니다. **scanf_s** 현재 UNICODE 스트림에서의 입력을 지원 하지 않습니다.

있는 이러한 함수 버전은 **_l** 제외은 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 하 고 접미사는 동일 합니다.

와 달리 **scanf** 및 **wscanf**, **scanf_s** 및 **wscanf_s** 버퍼 크기를 기준으로 모든 입력 형식의매개변수를지정해야**c**, **C**, **s**, **S**, 또는 컨트롤 집합에 포함 된 문자열 **[]** 합니다. 버퍼 크기는 버퍼 또는 변수에 대한 포인터 뒤에 바로 추가 매개 변수로 전달됩니다. 예를 들어 문자열을 읽고 있는 경우 해당 문자열에 대한 버퍼 크기가 다음과 같이 전달됩니다.

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

버퍼 크기에는 종료 null이 포함되어 있습니다. 너비 지정 필드를 사용하면 읽은 토큰이 버퍼에 맞는지 확인할 수 있습니다. 너비 지정 필드가 사용되지 않으며 읽은 토큰이 너무 커서 버퍼에 맞지 않는 경우 버퍼에는 아무것도 기록되지 않습니다.

> [!NOTE]
> 크기 매개 변수는 형식 **서명 되지 않은**이 아니라 **size_t**합니다. 정적 캐스트를 사용 하 여 변환할는 **size_t** 값을 **서명 되지 않은** 64 비트에 대 한 빌드 구성 합니다.

다음 예제에서는 버퍼 크기 매개 변수가 바이트가 아닌 문자의 최대 수를 설명한다는 사실을 보여 줍니다. 에 대 한 호출에서 **wscanf_s**, 버퍼 형식에 의해 지정 되는 문자 너비 서식 지정자에 의해 지정 되는 문자 너비와 일치 하지 않습니다.

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

**S** 형식 지정자는 "함수에서 지 원하는 기본 너비 반대" 인 문자 너비의 사용을 나타냅니다. 문자 너비는 싱글바이트이지만 함수는 더블바이트 문자를 지원합니다. 이 예제에서는 문자열에서 최대 9자의 싱글바이트 와이드 문자를 읽고 해당 문자를 더블바이트 와이드 문자 버퍼에 넣습니다. 문자는 싱글바이트 값으로 처리됩니다. 처음 두 문자는 `ws[0]`에 저장되고, 두 번째 두 문자는 `ws[1]`에 저장되는 방식입니다.

문자의 경우 다음과 같이 단일 문자를 읽을 수 있습니다.

```C
char c;
scanf_s("%c", &c, 1);
```

null로 끝나는 문자열이 아닌 문자열에 대한 여러 문자를 읽을 때 정수는 너비 지정 및 버퍼 크기로 사용됩니다.

```C
char c[4];
scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated
```

자세한 내용은 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

자세한 내용은 [서식 지정 필드: scanf 함수 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**scanf_s**, **_scanf_s_l**|\<stdio.h>|
|**wscanf_s**, **_wscanf_s_l**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 지원 되지 않습니다. 콘솔을 사용 하는 연결 된 표준 스트림 핸들 **stdin**, **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_scanf_s.c
// This program uses the scanf_s and wscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int      i,
            result;
   float    fp;
   char     c,
            s[80];
   wchar_t  wc,
            ws[80];

   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,
           wc, s, ws);
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,
            c, wc, s, ws);
}
```

이 프로그램을 실행하면 이 입력이 제공될 때 다음 출력이 생성됩니다.

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
