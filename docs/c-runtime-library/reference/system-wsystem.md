---
title: system, _wsystem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- system
- _wsystem
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tsystem
- _wsystem
dev_langs:
- C++
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca44648ed378d4484b8e4c32a38a6780b3eddd53
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="system-wsystem"></a>system, _wsystem

명령을 실행합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int system(
   const char *command
);
int _wsystem(
   const wchar_t *command
);
```

### <a name="parameters"></a>매개 변수

*command*<br/>
실행할 명령입니다.

## <a name="return-value"></a>반환 값

경우 *명령* 은 **NULL** 명령 인터프리터가 발견 되 면 0이 아닌 값을 반환 합니다. 명령 인터프리터가 없으면 0을 반환 하 고 설정 **errno** 를 **ENOENT**합니다. 경우 *명령* 않습니다 **NULL**, **시스템** 명령 인터프리터에 의해 반환 되는 값을 반환 합니다. 명령 인터프리터가 값 0을 반환할 때만 값 0을 반환합니다. 반환 값은-1은 오류를 나타내며 및 **errno** 다음 값 중 하나로 설정 됩니다.

|||
|-|-|
**E2BIG**|인수 목록(시스템에 따라 다름)이 너무 큽니다.
**ENOENT**|명령 인터프리터를 찾을 수 없습니다.
**ENOEXEC**|명령 인터프리터 파일 형식이 올바르지 않아서 실행할 수 없습니다.
**ENOMEM**|메모리가 부족하여 명령을 실행할 수 없습니다. 사용 가능한 메모리가 손상되었거나 잘못된 블록이 있습니다. 이는 호출 프로세스가 제대로 할당되지 않았음을 나타냅니다.

이러한 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**시스템** 전달 함수 *명령* 을 명령 해석기를 실행 하는 운영 체제 명령으로는 문자열입니다. **시스템** 사용 하 여는 **COMSPEC** 및 **경로** 환경 변수를 찾을 명령 인터프리터 파일 CMD.exe 합니다. 경우 *명령* 은 **NULL**, 함수는 명령 인터프리터가 존재 하는지 여부를 확인 합니다.

사용 하 여 명시적으로 플러시 해야 [fflush](fflush.md) 또는 [_flushall](flushall.md)를 호출 하기 전에 모든 스트림을 닫아야 **시스템**합니다.

**_wsystem** 의 와이드 문자 버전이 **시스템**; *명령* 인수를 **_wsystem** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**system**|**system**|**_wsystem**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**system**|\<process.h> 또는 \<stdlib.h>|
|**_wsystem**|\<process.h>, \<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 예에서는 **시스템** 를 텍스트 파일을 입력 합니다.

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crtsystemtxt"></a>입력: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Line one.
Line two.
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
