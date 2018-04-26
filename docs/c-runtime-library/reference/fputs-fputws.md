---
title: fputs, fputws | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fputs
- fputws
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fputs
- fputws
- _fputts
dev_langs:
- C++
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c21c8d3ea7253904aedc0e5f64c89f20dd70088b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="fputs-fputws"></a>fputs, fputws

스트림에 문자열을 씁니다.

## <a name="syntax"></a>구문

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
출력 문자열입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 성공할 경우 음수가 아닌 값을 반환합니다. 오류 발생 시 **fputs** 및 **fputws** 반환 **EOF**합니다. 경우 *str* 또는 *스트림* 가 null 포인터 이면 이러한 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된, 이러한 함수 설정 **errno** 를 **EINVAL** 차례로 **fputs** 반환 **EOF**, 및  **fputws** 반환 **WEOF**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수 복사본 *str* 출력에 *스트림* 현재 위치에 있습니다. **fputws** 와이드 문자 인수를 복사 *str* 를 *스트림* 열리는지에 따라 와이드 문자 문자열 또는 멀티 바이트 문자열 *스트림*각각 텍스트 모드 또는 이진 모드에서 열립니다. 어떤 함수도 null 종결 문자를 복사하지 않습니다.

스트림이 ANSI 모드에서 열리는 경우 두 함수는 동일하게 작동합니다. **fputs** 현재 UNICODE 스트림에 출력을 지원 하지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputts**|**fputs**|**fputs**|**fputws**|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fputs**|\<stdio.h>|
|**fputws**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 지원 되지 않습니다. 콘솔에 연결된 된 표준 스트림 핸들-**stdin**, **stdout**, 및 **stderr**-C 런타임 함수 UWP 앱에서 사용할 수 있는 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
