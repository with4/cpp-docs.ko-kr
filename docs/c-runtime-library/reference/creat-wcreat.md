---
title: _creat, _wcreat | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6b987faa30439f0f374838fe7fcd4d942b8cc7
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="creat-wcreat"></a>_creat, _wcreat

새 파일을 만듭니다. **_creat** 및 **_wcreat** 더 이상 사용 되지 않으므로 사용 [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) 대신 합니다.

## <a name="syntax"></a>구문

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
새 파일의 이름입니다.

*pmode*<br/>
권한 설정

## <a name="return-value"></a>반환 값

이러한 함수는 성공하는 경우 생성된 파일에 파일 설명자를 반환합니다. 그렇지 않으면 함수는-1을 반환 하 고 설정 **errno** 다음 표와 같이 합니다.

|**errno** 설정|설명|
|---------------------|-----------------|
|**EACCES**|*filename* 기존 읽기 전용 파일을 지정 하거나 파일 대신 디렉터리를 지정 합니다.|
|**EMFILE**|사용 가능한 추가 파일 설명자가 없습니다.|
|**ENOENT**|지정된 파일을 찾을 수 없습니다.|

경우 *filename* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는이 함수를 이러한 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된, 이러한 함수 설정 **errno** 를 **EINVAL** 고-1을 반환 합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

**_creat** 함수는 새 파일을 만듭니다. 또는 열리고 기존 자릅니다. **_wcreat** 의 와이드 문자 버전이 **_creat**; *filename* 인수를 **_wcreat** 는 와이드 문자 문자열입니다. **_wcreat** 및 **_creat** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

으로 지정한 파일이 있으면 *filename* 존재 하지 않는 새 파일을 지정 된 권한 설정을 사용 하 여 만들어지고 쓰기용으로 열입니다. 파일이 이미 존재 하 고 사용 권한 설정에 따라 쓰기를 허용 **_creat** 자릅니다 파일을 길이 0, 이전 내용을 제거 하 고 쓰기 위해 엽니다. 사용 권한 설정을 *pmode*, 새로 만든된 파일에만 적용 됩니다. 새 파일은 처음으로 닫힌 이후 지정된 권한 설정을 받습니다. 정수 식 *pmode* 매니페스트 상수 중 하나 또는 모두 포함 **_S_IWRITE** 및 **_S_IREAD**SYS\Stat.h에 정의 된 합니다. 두 상수가 지정 하는 경우와 비트 가입 or 연산자 ( **&#124;** ). *pmode* 매개 변수는 다음 값 중 하나로 설정 됩니다.

|값|정의|
|-----------|----------------|
|**_S_IWRITE**|쓰기를 허용합니다.|
|**_S_IREAD**|읽기를 허용합니다.|
|**_S_IREAD** &AMP;#124; **_S_IWRITE**|읽기 및 쓰기를 허용합니다.|

쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. 모든 파일을 항상 읽을 수 있으므로 쓰기 전용 권한을 부여할 수 없습니다. 모드 **_S_IWRITE** 및 **_S_IREAD** | **_S_IWRITE** 동일 합니다. 사용 하 여 연 파일 **_creat** 는 항상 호환 모드로 열립니다 (참조 [_sopen](sopen-wsopen.md))와 **_SH_DENYNO**합니다.

**_creat** 적용 하는 현재 파일 권한 마스크를 *pmode* 사용 권한을 설정 하기 전에 (참조 [_umask](umask.md)). **_creat** 주로 이전 라이브러리와의 호환성을 위해 제공 됩니다. 에 대 한 호출 **_open** 와 **_O_CREAT** 및 **_O_TRUNC** 에 *oflag* 매개 변수는 **_creat**및는 새 코드에 대 한 것이 좋습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> 또는 \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
