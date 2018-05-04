---
title: freopen_s, _wfreopen_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfreopen_s
- freopen_s
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
- freopen_s
- _tfreopen_s
- _wfreopen_s
dev_langs:
- C++
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04b136a46672838fd6ee554668353d92796abc7e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="freopens-wfreopens"></a>freopen_s, _wfreopen_s

파일 포인터를 다시 할당합니다. 이러한 버전의 [freopen, _wfreopen](freopen-wfreopen.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
errno_t freopen(
   FILE** pFile,
   const char *path,
   const char *mode,
   FILE *stream
);
errno_t _wfreopen(
   FILE** pFile,
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
호출에서 제공되는 파일 포인터에 대한 포인터입니다.

*path*<br/>
새 파일의 경로입니다.

*모드*<br/>
허용되는 액세스 형식입니다.

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 오류 코드를 반환합니다. 오류가 발생하면 원래 파일이 닫힙니다.

## <a name="remarks"></a>설명

**freopen_s** 함수는 현재 연결 된 파일을 닫습니다 *스트림* 재지정 *스트림* 로 지정 된 파일에 *경로* . **_wfreopen_s** 의 와이드 문자 버전이 **_freopen_s**; *경로* 및 *모드* 에 대 한 인수 **_wfreopen_s** 됩니다 와이드 문자 문자열입니다. **_wfreopen_s** 및 **_freopen_s** 동일 하 게 작동 합니다.

경우 *pFile*, *경로*, *모드*, 또는 *스트림* 는 **NULL**, if 또는 *경로* 이 빈 문자열인 경우에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는이 함수를 이러한 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된, 이러한 함수 설정 **errno** 를 **EINVAL** 다음 다시 돌아와 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**freopen_s** 은 일반적으로 리디렉션하는 데 사용 미리 열린된 파일 **stdin**, **stdout**, 및 **stderr** 사용자가 지정한 파일에 있습니다. 와 연결 된 새 파일 *스트림* 으로 연 *모드*이며 다음과 같이 파일에 대해 요청 된 액세스 형식을 지정 하는 문자 문자열:

|*모드*|액세스|
|-|-|
**"r"**|읽기 위해 엽니다. 파일이 존재 하지 않거나 찾을 수 없는 경우는 **freopen_s** 호출이 실패 합니다.
**"w"**|쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다.
**"a"**|새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다.
**"r+"**|읽고 쓰기 위해 엽니다. 파일이 있어야 합니다.
**"w+"**|읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다.
**"a+"**|읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다.

사용 하 여는 **"w"** 및 **"w +"** 기존 파일을 제거할 수 있으므로 신중 하 게 입력 합니다.

와 파일이 열릴 때의 **"a"** 또는 **"a +"** 액세스 형식을 모든 쓰기 작업이 파일의 끝에서 발생 합니다. 파일 포인터를 사용 하 여 변경 될 수 있지만 [fseek](fseek-fseeki64.md) 또는 [되감기](rewind.md), 파일 포인터는 항상 다시 이동 파일의 끝에 쓰기 작업을 수행 하기 전에. 따라서 기존 데이터를 덮어쓸 수 없습니다.

**"a"** 모드에서는 파일에 추가 하기 전에 EOF 표식을 제거 하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. **"a +"** 모드에서는 파일에 추가 하기 전에 EOF 표식을 제거 합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. **"a +"** 모드는 CTRL + Z EOF 표식으로 종료 되는 스트림 파일에 추가 해야 합니다.

경우는 **"r +"**, **"w +"**, 또는 **"a +"** 액세스 형식을 지정한 경우 읽기와 쓰기가 모두 허용 됩니다 ("업데이트" 용으로 열립니다, 파일이 업데이트용). 그러나 읽기와 쓰기를 전환할 때는 먼저 [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) 또는 [rewind](rewind.md) 작업이 있어야 합니다. 에 대 한 현재 위치를 지정할 수는 [fsetpos](fsetpos.md) 또는 [fseek](fseek-fseeki64.md) 작업을 원하는 경우. 위의 값 외에 다음 문자 중 하나에 포함할 수 있습니다는 *모드* 새 줄에 대해 변환 모드를 지정 하는 문자열입니다.

|*모드* 한정자|변환 모드|
|-|-|
**t**|텍스트(변환됨) 모드에서 엽니다.
**b**|이진(변환되지 않음) 모드에서 엽니다. 캐리지 리턴 및 줄 바꿈 문자를 포함하는 변환은 표시되지 않습니다.

텍스트 (변환 됨) 모드에서 캐리지 리턴-줄 바꿈 (CR-LF) 조합은 입력;에 단일 줄 바꿈 (LF) 문자로 변환 됩니다. LF 문자는 출력 시 CR-LF 조합으로 변환 합니다. 또한 CTRL+Z는 입력 시 파일 끝 문자로 변환됩니다. 에 대해 쓰기 및 읽기용으로 나 열려 있는 파일에서 **"a +"**, 런타임 라이브러리 파일의 끝에 CTRL + Z가 있는지 확인 하 고이 가능한 경우 제거 합니다. 사용 하 여 때문에 이렇게 [fseek](fseek-fseeki64.md) 및 [ftell](ftell-ftelli64.md) 파일 내에서 이동할 발생할 수 있습니다 [fseek](fseek-fseeki64.md) 파일의 끝 부분에서 제대로 동작 하지 합니다. **t** 옵션은 Microsoft 확장 이므로 ANSI 이식성을 원할 경우 사용 하지 않는 해야 합니다.

경우 **t** 또는 **b** 제공 되지 않습니다 *모드*, 기본 변환 모드는 전역 변수에 의해 정의 됩니다 [_fmode](../../c-runtime-library/fmode.md)합니다. 경우 **t** 또는 **b** 맨 앞에 인수, 함수 실패 및 반환 **NULL**합니다.

텍스트 모드와 이진 모드에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**freopen_s**|\<stdio.h>|
|**_wfreopen_s**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 지원 되지 않습니다. 콘솔을 사용 하는 연결 된 표준 스트림 핸들 **stdin**, **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_freopen_s.c
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   errno_t err;
   // Reassign "stderr" to "freopen.out":
   err = freopen_s( &stream, "freopen.out", "w", stderr );

   if( err != 0 )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
