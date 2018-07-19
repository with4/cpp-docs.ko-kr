---
title: _sopen_s, _wsopen_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _sopen_s
- _wsopen_s
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
- _sopen_s
- wsopen_s
- _wsopen_s
- sopen_s
dev_langs:
- C++
helpviewer_keywords:
- sopen_s function
- _wsopen_s function
- wsopen_s function
- opening files, for sharing
- files [C++], opening
- _sopen_s function
- files [C++], sharing
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c94219ff0b357e7627528d68938ec430fd8dc14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418486"
---
# <a name="sopens-wsopens"></a>_sopen_s, _wsopen_s

공유할 파일을 엽니다. 이러한 버전의 [_sopen 및 _wsopen](sopen-wsopen.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
errno_t _sopen_s(
   int* pfh,
   const char *filename,
   int oflag,
   int shflag,
   int pmode
);
errno_t _wsopen_s(
   int* pfh,
   const wchar_t *filename,
   int oflag,
   int shflag,
   int pmode,
);
```

### <a name="parameters"></a>매개 변수

*pfh*<br/>
파일 핸들 또는 오류 발생 시 -1

*filename*<br/>
파일 이름.

*oflag*<br/>
허용되는 연산의 종류

*shflag*<br/>
허용되는 공유의 종류

*pmode*<br/>
권한 설정

## <a name="return-value"></a>반환 값

반환 값이 0이 아닌 오류; 나타냅니다. 이 경우 **errno** 다음 값 중 하나로 설정 됩니다.

|errno 값|조건|
|-|-|
**EACCES**| 지정된 경로가 디렉터리거나 파일이 읽기 전용인데 쓰기 위한 열기 작업을 시도했습니다.
**EEXIST**| **_O_CREAT** 및 **_O_EXCL** 플래그를 지정 하지만 *filename* 이미 있습니다.
**EINVAL**| 잘못 된 *oflag*, *shflag*, 또는 *pmode* 인수, 또는 *pfh* 또는 *filename* 는 null 포인터입니다.
**EMFILE**|사용 가능한 추가 파일 설명자가 없습니다.
**ENOENT**|파일 또는 경로를 찾을 수 없습니다.

함수에 잘못된 인수가 전달되면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 및 **EINVAL** 반환 됩니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

오류가 발생 하는 경우-1이를 통해 반환 *pfh* (하지 않는 한 *pfh* 가 null 포인터).

## <a name="remarks"></a>설명

**_sopen_s** 함수에서 지정한 파일을 열고 *filename* 정의한 대로 공유 읽기 또는 쓰기를 위해 파일을 준비 *oflag* 및 *shflag* . **_wsopen_s** 의 와이드 문자 버전이 **_sopen_s**; *filename* 인수를 **_wsopen_s** 는 와이드 문자 문자열입니다. **_wsopen_s** 및 **_sopen_s** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen_s**|**_sopen_s**|**_sopen_s**|**_wsopen_s**|

정수 식 *oflag* 하나 이상의 매니페스트 상수에 정의 되어 있는 결합 하 여 형식이 \<fcntl.h > 합니다. 상수 두 개 이상의 인수를 구성할 때 *oflag*, 비트 OR 연산자와 결합 됩니다 ( **&#124;** ).

|*oflag* 상수|동작|
|-|-|
**_O_APPEND**|모든 쓰기 작업 전에 파일 끝으로 파일 포인터를 이동합니다.
**_O_BINARY**|파일을 이진(변환되지 않음) 모드에서 엽니다. 이진 모드에 대한 설명은 [fopen](fopen-wfopen.md)을 참조하세요.
**_O_CREAT**|파일을 만든 다음 쓰기 위해 엽니다. 지정한 파일이 있으면 의미가 없습니다 *filename* 존재 합니다. *pmode* 인수는 필수 **_O_CREAT** 지정 됩니다.
**_O_CREAT** &AMP;#124; **_O_SHORT_LIVED**|파일을 임시로 만든 다음 가능한 경우 디스크로 플러시하지 않습니다. *pmode* 인수는 필수 **_O_CREAT** 지정 됩니다.
**_O_CREAT** &AMP;#124; **_O_TEMPORARY**|파일을 임시로 만듭니다. 마지막 파일 설명자가 닫히면 파일이 삭제됩니다. *pmode* 인수는 필수 **_O_CREAT** 지정 됩니다.
**_O_CREAT**&AMP;#124; ` _O_EXCL`|으로 지정한 파일이 있으면 오류 값을 반환 *filename* 존재 합니다. 와 함께 사용할 경우에 적용 됩니다. **_O_CREAT**합니다.
**_O_NOINHERIT**|공유 파일 설명자의 생성을 방지합니다.
**_O_RANDOM**|캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다.
**_O_RDONLY**|읽으려는 경우에만 파일을 엽니다. 함께 지정할 수 없습니다 **_O_RDWR** 또는 **_O_WRONLY**합니다.
**_O_RDWR**|읽고 쓰기 위해 파일을 엽니다. 함께 지정할 수 없습니다 **_O_RDONLY** 또는 **_O_WRONLY**합니다.
**_O_SEQUENTIAL**|캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다.
**_O_TEXT**|파일을 텍스트(변환됨) 모드에서 엽니다. 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [fopen](fopen-wfopen.md)을 참조하세요.
**_O_TRUNC**|파일을 열고 길이가 0이 되도록 자릅니다. 이 파일에는 쓰기 권한이 있어야 합니다. 함께 지정할 수 없습니다 **_O_RDONLY**합니다. **_O_TRUNC** 사용한 **_O_CREAT** 기존 파일을 열거나 파일을 만듭니다. **참고:** 는 **_O_TRUNC** 플래그 지정된 된 파일의 내용을 제거 합니다.
**_O_WRONLY**|쓰려는 경우에만 파일을 엽니다. 함께 지정할 수 없습니다 **_O_RDONLY** 또는 **_O_RDWR**합니다.
**_O_U16TEXT**|유니코드 UTF-16 모드에서 파일을 엽니다.
**_O_U8TEXT**|유니코드 UTF-8 모드에서 파일을 엽니다.
**_O_WTEXT**|유니코드 모드에서 파일을 엽니다.

파일 액세스 모드를 지정 하려면 지정 해야 **_O_RDONLY**, **_O_RDWR**, 또는 **_O_WRONLY**합니다. 액세스 모드의 기본값은 없습니다.

사용 하 여 파일을 유니코드 모드에서 열 때 **_O_WTEXT**, **_O_U8TEXT**, 또는 **_O_U16TEXT**입력, u t F-16으로 데이터 파일에서 읽은 데이터를 변환 하는 함수 형식으로 저장 **wchar_t**합니다. 유니코드 모드에서 연 파일에 쓰는 함수는 형식으로 저장 되는 utf-16 데이터가 포함 된 버퍼가 예상 **wchar_t**합니다. 이 파일이 UTF-8로 인코딩되면 UTF-16 데이터는 쓸 때 UTF-8로 변환되고 이 파일의 UTF-8로 인코딩된 내용은 읽을 때 UTF-16으로 변환됩니다. 유니코드 모드에서 홀수 바이트를 읽거나 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다. 프로그램에 UTF-8로 저장된 데이터를 읽거나 쓰려는 경우 유니코드 모드 대신 텍스트 또는 이진 파일 모드를 사용합니다. 필수 인코딩은 사용자가 변환해야 합니다.

경우 **_sopen_s** 사용 하 여 호출 **_O_WRONLY** | **_O_APPEND** (추가 모드) 및 **_O_WTEXT**, **_O_ U16TEXT**, 또는 **_O_U8TEXT**BOM을 읽은 먼저 읽기 및 쓰기를 위해 파일을 열려고 시도 차례로 쓰기 위해서만 다시 여세요. 읽고 쓰기 위해 파일을 여는데 실패하면 쓰기 위해서만 파일을 열고 유니코드 모드 설정에 기본값을 사용합니다.

인수 *shflag* 에 정의 된 다음 매니페스트 상수 중 하나로 구성 하는 상수 식 \<share.h > 합니다.

|*shflag* 상수|동작|
|-|-|
**_SH_DENYRW**|파일에 대한 읽기 및 쓰기 액세스를 거부합니다.
**_SH_DENYWR**|파일에 대한 쓰기 액세스를 거부합니다.
**_SH_DENYRD**|파일에 대한 읽기 액세스를 거부합니다.
**_SH_DENYNO**|읽기 및 쓰기 액세스 권한을 허용합니다.

*pmode* 인수는 항상에서 달리 필수 **_sopen**합니다. 지정 하는 경우 **_O_CREAT**파일이 없는 경우, *pmode* 새 파일이 처음 닫힐 때 설정 되는 파일의 권한 설정을 지정 합니다. 그렇지 않으면 *pmode* 는 무시 됩니다. *pmode* 매니페스트 상수 중 하나 또는 모두를 포함 하는 정수 식 **_S_IWRITE** 및 **_S_IREAD**에 정의 되어 있는 \<sys\stat.h > 합니다. 두 상수가 지정된 경우 비트 OR 연산자를 사용하여 결합합니다. 의미 *pmode* 는 다음과 같습니다.

|*pmode*|의미|
|-|-|
**_S_IREAD**|읽기만 허용합니다.
**_S_IWRITE**|쓰기를 허용합니다. 실제로는 읽기 및 쓰기를 모두 허용합니다.
**_S_IREAD** &AMP;#124; **_S_IWRITE**|읽기 및 쓰기를 허용합니다.

쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. Windows 운영 체제에서 모든 파일을 읽을 수 있지만 쓰기 전용 권한을 부여할 수는 없습니다. 따라서 **_S_IWRITE** 및 **_S_IREAD** | **_S_IWRITE** 동일 합니다.

**_sopen_s** 적용 하는 현재 파일 권한 마스크를 *pmode* 사용 권한을 설정 하기 전에. [_umask](umask.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_sopen_s**|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|
|**_wsopen_s**|\<io.h> 또는 \<wchar.h>|\<fcntl.h>, \<sys/types.h>, \<sys/stat.h>, \<share.h>|

**_sopen_s** 및 **_wsopen_s** 는 Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_locking](locking.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
