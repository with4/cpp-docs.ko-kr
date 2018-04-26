---
title: puts, _putws | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _putws
- puts
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
- _putts
- _putws
- puts
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a823106478e575f9b2d65bc4e739236098da5124
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="puts-putws"></a>puts, _putws

**stdout**에 문자열을 씁니다.

## <a name="syntax"></a>구문

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
출력 문자열입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되면 음수가 아닌 값을 반환합니다. 경우 **배치** 실패 하면 반환 **EOF**경우 **_putws** 실패 하면 반환 **WEOF**합니다. 경우 *str* 가 null 포인터에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하려면 허용한 경우 함수 설정 **errno** 를 **EINVAL** 다음 다시 돌아와 **EOF** 또는 **WEOF**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**배치** 쓰기 함수 *str* 표준 출력 스트림에 **stdout**, 문자열을 대체의 종료 null 문자 ('\0')는 줄 바꿈 문자 ('\n')의 출력 스트림입니다.

**_putws** 의 와이드 문자 버전이 **배치**; 스트림이 ANSI 모드에서 열리는 경우 두 함수는 동일 하 게 작동 합니다. **배치** 현재 출력 유니코드 스트림을 지원 하지 않습니다.

**_putwch** 현재 콘솔 로캘 설정을 사용 하 여 유니코드 문자를 씁니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 지원 되지 않습니다. 콘솔을 사용 하는 연결 된 표준 스트림 핸들 **stdin**, **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>출력

```Output
Hello world from puts!
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
