---
title: _chdir, _wchdir | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wchdir
- _chdir
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
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
dev_langs:
- C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61744ec875b057ae7d1b32703fb7ce5f813b5ff4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="chdir-wchdir"></a>_chdir, _wchdir

현재 작업 디렉터리를 변경합니다.

## <a name="syntax"></a>구문

```C
int _chdir(
   const char *dirname
);
int _wchdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>매개 변수

*dirname*<br/>
새 작업 디렉터리의 경로입니다.

## <a name="return-value"></a>반환 값

이러한 함수는 성공할 경우 0 값을 반환합니다. 반환 값이-1은 오류를 나타냅니다. 지정 된 경로 찾을 수 있으면 **errno** 로 설정 된 **ENOENT**합니다. 경우 *dirname* 가 null 인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수가-1을 반환 합니다.

## <a name="remarks"></a>설명

**_chdir** 로 지정 된 디렉터리를 현재 작업 디렉터리를 변경 하는 함수 *dirname*합니다. *dirname* 기존 디렉터리를 참조 해야 합니다. 이 함수는 모든 드라이브에서 현재 작업 디렉터리를 변경할 수 있습니다. 새 드라이브 문자에 지정 된 경우 *dirname*, 기본 드라이브 문자 변경 됩니다. 예를 들어 A가 기본 드라이브 문자이고 \BIN이 현재 작업 디렉터리이면 다음 호출에서 C 드라이브에 대한 현재 작업 디렉터리를 변경하고 C를 새 기본 드라이브로 설정합니다.

```C
_chdir("c:\temp");
```

선택적 백슬래시 문자를 사용 하는 경우 (**&#92;**) 경로, 두 개의 백슬래시를 배치 해야 (**&#92;&#92;**) C 문자열 리터럴에를 나타내는 단일 백슬래시 ( **&#92;**).

**_wchdir** 의 와이드 문자 버전이 **_chdir**; *dirname* 인수를 **_wchdir** 는 와이드 문자 문자열입니다. **_wchdir** 및 **_chdir** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mapping"></a>제네릭 텍스트 루틴 매핑:

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchdir**|**_chdir**|**_chdir**|**_wchdir**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_chdir**|\<direct.h>|\<errno.h>|
|**_wchdir**|\<direct.h> 또는 \<wchar.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_chdir.c
// arguments: C:\WINDOWS

/* This program uses the _chdir function to verify
   that a given directory exists. */

#include <direct.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int argc, char *argv[] )
{

   if(_chdir( argv[1] ) )
   {
      switch (errno)
      {
      case ENOENT:
         printf( "Unable to locate the directory: %s\n", argv[1] );
         break;
      case EINVAL:
         printf( "Invalid buffer.\n");
         break;
      default:
         printf( "Unknown error.\n");
      }
   }
   else
      system( "dir *.exe");
}
```

```Output
 Volume in drive C has no label.
 Volume Serial Number is 2018-08A1

 Directory of c:\windows

08/29/2002  04:00 AM         1,004,032 explorer.exe
12/17/2002  04:43 PM            10,752 hh.exe
03/03/2003  09:24 AM            33,792 ieuninst.exe
10/29/1998  04:45 PM           306,688 IsUninst.exe
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE
03/03/2003  09:24 AM            33,792 Q330994.exe
08/29/2002  04:00 AM           134,144 regedit.exe
02/28/2003  06:26 PM            46,352 setdebug.exe
08/29/2002  04:00 AM            15,360 TASKMAN.EXE
08/29/2002  04:00 AM            49,680 twunk_16.exe
08/29/2002  04:00 AM            25,600 twunk_32.exe
08/29/2002  04:00 AM           256,192 winhelp.exe
08/29/2002  04:00 AM           266,752 winhlp32.exe
              13 File(s)      2,249,184 bytes
               0 Dir(s)  67,326,029,824 bytes free
```

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
