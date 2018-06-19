---
title: _chdrive | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- chdrive
- _chdrive
dev_langs:
- C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f95169f62fa2eaf9c562bff463ad84c0827db9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394424"
---
# <a name="chdrive"></a>_chdrive

현재 작업 드라이브를 변경합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>매개 변수

*드라이브*<br/>
현재 작업 드라이브를 지정하는 1부터 26까지의 정수입니다(1 = A, 2 = B 등).

## <a name="return-value"></a>반환 값

현재 작업 드라이브가 변경된 경우 0이고, 변경되지 않으면 -1입니다.

## <a name="remarks"></a>설명

경우 *드라이브* 은 1부터 26 까지의 범위에서 벗어난 잘못 된 매개 변수 처리기가에 설명 된 대로 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 하는 경우는 **_chdrive** 함수가-1 반환 **errno** 로 설정 된 **EACCES**, 및 **_doserrno** 로설정되어 **ERROR_INVALID_DRIVE**합니다.

**_chdrive** 함수는 그 자체가 스레드로부터 안전하지 않은 **SetCurrentDirectory** 함수에 종속되므로 스레드로부터 안전하지 않습니다. 다중 스레드 응용 프로그램에서 **_chdrive**를 안전하게 사용하려면 고유한 스레드 동기화를 제공해야 합니다. 자세한 내용을 보려면 [MSDN 라이브러리](http://go.microsoft.com/fwlink/p/?linkid=150542)로 이동한 후 **SetCurrentDirectory**를 검색하세요.

**_chdrive** 함수는 현재 작업 드라이브만 변경합니다. **_chdir** 함수는 현재 작업 디렉터리를 변경합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_getdrive](getdrive.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
