---
title: fopen, _wfopen | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfopen
- fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b606f168448f833a8e244ad35e52faf4f0afd75
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405408"
---
# <a name="fopen-wfopen"></a>fopen, _wfopen

파일을 엽니다. 추가 매개 변수 유효성 검사를 수행하고 오류 코드를 반환하는 이 함수의 더 안전한 버전을 사용할 수 있습니다. [fopen_s, _wfopen_s](fopen-s-wfopen-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
FILE *fopen(
   const char *filename,
   const char *mode
);
FILE *_wfopen(
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
파일 이름.

*모드*<br/>
사용할 수 있는 액세스 종류입니다.

## <a name="return-value"></a>반환 값

각 함수는 열린 파일에 대한 포인터를 반환합니다. null 포인터 값은 오류를 나타냅니다. 경우 *filename* 또는 *모드* 은 **NULL** 또는 빈 문자열인 경우 이러한 함수에 설명 된 잘못 된 매개 변수 처리기를 트리거합니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우 이러한 함수가 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**fopen** 함수에 지정 된 파일을 엽니다 *filename*합니다. 기본적으로 반각 *filename* 문자열은 ANSI 코드 페이지 (CP_ACP)를 사용 하 여 해석 됩니다. Windows 데스크톱 응용 프로그램에서 이 페이지를 [SetFileApisToOEM](https://msdn.microsoft.com/library/windows/desktop/aa365534\(v=vs.85\).aspx) 함수를 사용하여 OEM 코드 페이지(CP_OEMCP)로 변경할 수 있습니다. 사용할 수 있습니다는 [AreFileApisANSI](https://msdn.microsoft.com/library/windows/desktop/aa363781\(v=vs.85\).aspx) 함수를 여부 *filename* ANSI 또는 시스템의 기본 OEM 코드 페이지를 사용 하 여 해석 됩니다. **_wfopen** 의 와이드 문자 버전이 **fopen**;에 대 한 인수 **_wfopen** 는 와이드 문자 문자열입니다. 그렇지 않으면 **_wfopen** 및 **fopen** 동일 하 게 작동 합니다. 사용 하 여 방금 **_wfopen** 파일 스트림에 사용 되는 코딩 된 문자 집합에는 영향을 주지 않습니다.

**fopen** 실행 지점에서 파일 시스템에 유효한 경로 허용 합니다. **fopen** 코드를 실행 하는 시스템에서 공유에 액세스할 권한이 매핑된 네트워크 드라이브 또는 매핑된 드라이브는 실행 시간에 포함 하는 경로 및 UNC 경로 허용 합니다. 에 대 한 경로 생성할 때 **fopen**, 드라이브, 경로 또는 네트워크 공유 되도록 실행 환경에서 사용할 수 있는지 확인 합니다. 슬래시(/) 또는 백슬래시(\\)를 경로의 디렉터리 구분 기호로 사용할 수 있습니다.

파일에서 추가 작업을 수행하기 전에 항상 반환 값을 검사하여 포인터가 NULL인지 여부를 확인하세요. 오류가 발생할 때 전역 변수 **errno** 설정 되 고 특정 오류 정보를 가져오는 데 사용할 수 있습니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="unicode-support"></a>유니코드 지원

**fopen** 은 유니코드 파일 스트림을 지원 합니다. 유니코드 파일을 열려면 전달는 **ccs** 에 원하는 인코딩을 지정 하는 플래그 **fopen**다음과 같이 합니다.

> **파일 *fp fopen = ("newfile.txt", "rt + ccs =**_인코딩_**");**

허용 되는 값의 *인코딩* 는 **유니코드**, **u t F-8**, 및 **u t F-16LE**합니다.

파일은 유니코드 모드에서 열면 입력된 함수 형식으로 저장 된 데이터를 u t F-16으로 파일에서 읽은 데이터를 변환 하는 **wchar_t**합니다. 유니코드 모드에서 연 파일에 쓰는 함수는 형식으로 저장 되는 utf-16 데이터가 포함 된 버퍼가 예상 **wchar_t**합니다. 이 파일이 UTF-8로 인코딩되면 UTF-16 데이터는 쓸 때 UTF-8로 변환되고 이 파일의 UTF-8로 인코딩된 내용은 읽을 때 UTF-16으로 변환됩니다. 유니코드 모드에서 홀수 바이트를 읽거나 쓰려고 하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 오류가 발생합니다. 프로그램에 UTF-8로 저장된 데이터를 읽거나 쓰려는 경우 유니코드 모드 대신 텍스트 또는 이진 파일 모드를 사용합니다. 필수 인코딩은 사용자가 변환해야 합니다.

파일이 이미 있고 읽기 또는 추가용으로 열려 있는 경우 BOM(바이트 순서 표시)(파일에 있는 경우)에 따라 인코딩이 결정됩니다. 지정 된 인코딩보다 우선 순위는 BOM 인코딩이 **ccs** 플래그입니다. **ccs** 인코딩은 BOM이 없거나 파일이 새 파일을 하는 경우 사용만 됩니다.

> [!NOTE]
> BOM 검색은 유니코드 모드로 열려 있는 파일에에 적용 됩니다 (즉, 전달한는 **ccs** 플래그).

다음 표에서 다양 한에 사용 되는 모드를 간단히 설명 **ccs** 에 지정 된 **fopen** 및 파일에 바이트 순서 표시 합니다.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs 플래그 및 BOM을 기반으로 사용되는 인코딩

|ccs 플래그|BOM이 없거나 새 파일|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**유니코드**|**UTF-16LE**|**U T F-8**|**UTF-16LE**|
|**U T F-8**|**U T F-8**|**U T F-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**U T F-8**|**UTF-16LE**|

유니코드 모드에서 쓰도록 파일을 열면 BOM이 파일에 자동으로 기록됩니다.

경우 *모드* 은 **"a, ccs =**_인코딩_**"**, **fopen** 먼저 읽기를 사용 하 여 파일을 열려고 시도 및 쓰기 액세스입니다. 성공하면 BOM을 읽고 파일에 대한 인코딩을 결정하고, 실패하면 파일에 대한 기본 인코딩을 사용합니다. 두 경우 모두 **fopen** 쓰기 전용 액세스를 사용 하 여 파일을 다시 엽니다 다음 됩니다. (이에 적용 됩니다 **"a"** 모드에 대해서만 하지 **"a +"** 모드입니다.)

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen**|**fopen**|**fopen**|**_wfopen**|

문자열 *모드* 다음과 같이 파일에 대해 요청 되는 액세스 종류를 지정 합니다.

|*모드*|액세스|
|-|-|
**"r"**|읽기 위해 엽니다. 파일이 존재 하지 않거나 찾을 수 없는 경우는 **fopen** 호출이 실패 합니다.
**"w"**|쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다.
**"a"**|새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다.
**"r+"**|읽고 쓰기 위해 엽니다. 파일이 있어야 합니다.
**"w+"**|읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다.
**"a+"**|읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다.

사용 하 여 파일을 열 때는 **"a"** 액세스 형식 또는 **"a +"** 액세스 형식을 모든 쓰기 작업이 파일의 끝에서 발생 합니다. 사용 하 여 파일 포인터 위치를 변경할 수 [fseek](fseek-fseeki64.md) 또는 [되감기](rewind.md)을 항상 다시 이동 파일의 끝에 쓰기 작업을 수행 하기 전에 하지만 합니다. 따라서 기존 데이터를 덮어쓸 수 없습니다.

**"a"** 모드는 파일에 추가 하기 전에 EOF 표식을 제거 하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. 파일을 추가 하기 전에 **"a +"** 모드에서는 EOF 표식을 제거 합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. **"a +"** 모드는 CTRL + Z EOF 표식으로 종료 되는 스트림 파일에 추가 해야 합니다.

경우는 **"r +"**, **"w +"**, 또는 **"a +"** 액세스 형식을 지정한 경우 읽기와 쓰기가 모두 사용 하도록 설정 ("업데이트" 용으로 열립니다, 파일이 업데이트용). 하지만 읽기에서 쓰기로 전환할 경우 입력 작업 시 EOF 표식이 필요합니다. EOF가 없는 경우 사이에 파일 위치 지정 함수를 호출해야 합니다. 파일 위치 지정 함수는 **fsetpos**, [fseek](fseek-fseeki64.md), 및 [rewind](rewind.md)합니다. 에 대 한 중간 호출을 사용 해야 쓰기에서 읽기로 전환할 때 **fflush** 또는 파일 위치 지정 함수입니다.

이전 값 이외에 다음 문자에 추가 될 수 *모드* 줄 바꿈 문자에 대 한 변환 모드를 지정할 수 있습니다.

|*모드* 한정자|변환 모드|
|-|-|
**t**|텍스트(변환됨) 모드에서 엽니다.
**b**|이진(변환되지 않음) 모드에서 엽니다. 캐리지 리턴 및 줄 바꿈 문자를 포함하는 변환은 표시되지 않습니다.

텍스트 모드에서 CTRL + Z는 입력에서 EOF 문자로 해석 됩니다. 사용 하 여 읽기/쓰기를 위해 연 파일에서 **"a +"**, **fopen** 파일의 끝에 CTRL + Z가 있는지 확인 하 고 가능한 경우이 제거 합니다. 사용 하 여 때문에 이렇게 [fseek](fseek-fseeki64.md) 및 **ftell** CTRL + Z로 끝나는 않을 파일 내에서 이동할 수 [fseek](fseek-fseeki64.md) 파일의 끝 부분에서 제대로 동작 합니다.

텍스트 모드에서 캐리지 리턴-줄 바꿈 조합은 입력 시 단일 줄 바꿈으로 변환 되 고 줄 바꿈 문자는 출력에서 캐리지 리턴-줄 바꿈 조합으로 변환 합니다. 유니코드 스트림 I/O 함수가 텍스트 모드에서 작동할 경우(기본값) 소스 또는 대상 스트림은 멀티바이트 문자 시퀀스로 간주됩니다. 따라서 유니코드 스트림 입력 함수는 **mbtowc** 함수 호출과 마찬가지로 멀티바이트 문자를 와이드 문자로 변환합니다. 동일한 이유로 유니코드 스트림 출력 함수는 **wctomb** 함수 호출과 마찬가지로 와이드 문자를 멀티바이트 문자로 변환합니다.

경우 **t** 또는 **b** 제공 되지 않습니다 *모드*, 기본 변환 모드는 전역 변수에 의해 정의 됩니다 [_fmode](../../c-runtime-library/fmode.md)합니다. 경우 **t** 또는 **b** 맨 앞에 인수, 함수 실패 및 반환 **NULL**합니다.

유니코드 및 멀티바이트 스트림 I/O에서 텍스트 모드 및 이진 모드를 사용하는 방법에 대한 자세한 내용은 [Text and Binary Mode File I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.

다음 옵션에 추가 될 수 *모드* 추가 동작을 지정할 수 있습니다.

|*모드* 한정자|동작|
|-|-|
**c**|연결 된 작업에 대 한 커밋 플래그를 사용 *filename* 파일 버퍼의 내용이 디스크에 직접 기록 되도록 **fflush** 또는 **_flushall** 호출 됩니다.
**n**|연결 된 작업에 대 한 커밋 플래그를 다시 설정 *filename* 를 "커밋 안 함." 이 값이 기본값입니다. 또한 프로그램을 COMMODE.OBJ와 연결할 경우 전역 커밋 플래그를 재정의합니다. 프로그램을 COMMODE.OBJ와 명시적으로 연결하지 않을 경우 전역 커밋 플래그 기본값은 "커밋 안 함"입니다( [Link Options](../../c-runtime-library/link-options.md)참조).
**N**|자식 프로세스에서 파일을 상속하지 않도록 지정합니다.
**S**|캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다.
**R**|캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다.
**T**|파일을 임시 파일로 지정합니다. 가능하면 디스크에 플러시되지 않습니다.
**D**|파일을 임시 파일로 지정합니다. 마지막 파일 포인터를 닫을 때 삭제됩니다.
**ccs =**_인코딩_|인코딩된 문자를 사용 하도록 설정 지정 (중 하나 **u t F-8**, **u t F-16LE**, 또는 **유니코드**)이이 파일에 대 한 합니다. ANSI 인코딩을 원할 경우 지정되지 않은 상태로 둡니다.

에 유효한 문자는 *모드* 에 사용 되는 문자열 **fopen** 및 **_fdopen** 에 해당 *oflag* 에사용되는인수[_open](open-wopen.md) 및 [_sopen](sopen-wsopen.md)다음과 같이 합니다.

|문자 *모드* 문자열|해당 *oflag* _open/_sopen에 대 한 값|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (일반적으로 **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_APPEND * *)|
|**+**|**_O_RDWR** &#124; **_O_APPEND** (일반적으로 **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**w**|**_O_WRONLY** (일반적으로 **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_TRUNC * *)|
|**w +**|**_O_RDWR** (일반적으로 **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**c**|없음|
|**n**|없음|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs 유니코드 =**|**_O_WTEXT**|
|**ccs = u t F-8**|**_O_UTF8**|
|**ccs u t F-16LE =**|**_O_UTF16**|

사용 중인 경우 **rb** 모드 않아도 코드를 이식 하 고 큰 파일의 대부분을 읽어야 하거나 네트워크 성능이 문제가 되지 않을 수도 있습니다 여부 메모리를 사용 하도록 매핑된 Win32 파일을 옵션으로 합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fopen**|\<stdio.h>|
|**_wfopen**|\<stdio.h> 또는 \<wchar.h>|

**_wfopen** Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**c**, **n**, **t**, **S**, **R**, **T**, 및 **D**  *모드* 옵션에 대 한 Microsoft 확장은 **fopen** 및 **_fdopen** 이므로 ANSI 이식성을 원할 경우 사용할 수 없습니다.

## <a name="example-1"></a>예제 1

다음 프로그램은 두 파일을 엽니다.  사용 하 여 **fclose** 첫 번째 파일을 닫고 및 **_fcloseall** 를 나머지 파일을 모두 닫습니다.

```C
// crt_fopen.c
// compile with: /W3
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   int numclosed;

   // Open for read (will fail if file "crt_fopen.c" does not exist)
   if( (stream  = fopen( "crt_fopen.c", "r" )) == NULL ) // C4996
   // Note: fopen is deprecated; consider using fopen_s instead
      printf( "The file 'crt_fopen.c' was not opened\n" );
   else
      printf( "The file 'crt_fopen.c' was opened\n" );

   // Open for write
   if( (stream2 = fopen( "data2", "w+" )) == NULL ) // C4996
      printf( "The file 'data2' was not opened\n" );
   else
      printf( "The file 'data2' was opened\n" );

   // Close stream if it is not NULL
   if( stream)
   {
      if ( fclose( stream ) )
      {
         printf( "The file 'crt_fopen.c' was not closed\n" );
      }
   }

   // All other files are closed:
   numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="example-2"></a>예제 2

다음 프로그램은 텍스트 모드에서 유니코드 인코딩을 포함하는 파일을 만들거나 덮어씁니다(파일이 있는 경우).  그런 다음 파일에 두 문자열을 쓰고 파일을 닫습니다. 출력 파일은 _wfopen_test.xml이며, 출력 섹션의 데이터를 포함합니다.

```C
// crt__wfopen.c
// compile with: /W3
// This program creates a file (or overwrites one if
// it exists), in text mode using Unicode encoding.
// It then writes two strings into the file
// and then closes the file.

#include <stdio.h>
#include <stddef.h>
#include <stdlib.h>
#include <wchar.h>

#define BUFFER_SIZE 50

int main(int argc, char** argv)
{
    wchar_t str[BUFFER_SIZE];
    size_t  strSize;
    FILE*   fileHandle;

    // Create an the xml file in text and Unicode encoding mode.
    if ((fileHandle = _wfopen( L"_wfopen_test.xml",L"wt+,ccs=UNICODE")) == NULL) // C4996
    // Note: _wfopen is deprecated; consider using _wfopen_s instead
    {
        wprintf(L"_wfopen failed!\n");
        return(0);
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"<xmlTag>\n");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"</xmlTag>");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Close the file.
    if (fclose(fileHandle))
    {
        wprintf(L"fclose failed!\n");
    }
    return 0;
}
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
