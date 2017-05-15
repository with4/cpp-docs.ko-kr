---
title: "fopen, _wfopen | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 56
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 7d432ab9e8bdb6f386eb6fe4fbb24d218d6a2071
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="fopen-wfopen"></a>fopen, _wfopen
파일을 엽니다. 추가 매개 변수 유효성 검사를 수행하고 오류 코드를 반환하는 이 함수의 더 안전한 버전을 사용할 수 있습니다. [fopen_s, _wfopen_s](../../c-runtime-library/reference/fopen-s-wfopen-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
FILE *fopen(   
   const char *filename,  
   const char *mode   
);  
FILE *_wfopen(   
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 파일 이름.  
  
 `mode`  
 사용할 수 있는 액세스 종류입니다.  
  
## <a name="return-value"></a>반환 값  
 각 함수는 열린 파일에 대한 포인터를 반환합니다. null 포인터 값은 오류를 나타냅니다. `filename` 또는 `mode`가 `NULL`이거나 빈 문자열인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 트리거합니다. 계속해서 실행하도록 허용된 경우, 이러한 함수는 `NULL` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `fopen` 함수는 `filename`에 지정된 파일을 엽니다. 기본적으로 반각 `filename` 문자열은 ANSI 코드 페이지(CP_ACP)를 사용하여 해석됩니다. Windows 데스크톱 응용 프로그램에서 이 페이지를 [SetFileApisToOEM](https://msdn.microsoft.com/library/windows/desktop/aa365534\(v=vs.85\).aspx) 함수를 사용하여 OEM 코드 페이지(CP_OEMCP)로 변경할 수 있습니다. [AreFileApisANSI](https://msdn.microsoft.com/library/windows/desktop/aa363781\(v=vs.85\).aspx) 함수를 사용하여 `filename` 이 ANSI 코드 페이지를 사용하여 해석되는지 아니면 시스템의 기본 OEM 코드 페이지를 사용하여 해석되는지 여부를 결정할 수 있습니다. `_wfopen` 는 `fopen`의 와이드 문자 버전이며, `_wfopen` 에 대한 인수는 와이드 문자 문자열입니다. 그렇지 않으면 `_wfopen` 과 `fopen` 은 동일하게 작동합니다. `_wfopen` 만 사용할 경우 파일 스트림에 사용되는 코딩된 문자 집합에 영향을 주지 않습니다.  
  
 `fopen` 은 실행 시점에 파일 시스템에 유효한 경로를 허용하고, `fopen` 은 매핑된 네트워크 드라이브를 포함하는 경로 및 UNC 경로를 허용합니다(코드를 실행하는 시스템에서 실행 시점에 공유 또는 매핑된 드라이브에 액세스할 수 있는 경우). `fopen`에 대한 경로를 생성할 때 드라이브, 경로 또는 네트워크 공유를 실행 환경에서 사용할 수 있는지를 확인합니다. 슬래시(/) 또는 백슬래시(\\)를 경로의 디렉터리 구분 기호로 사용할 수 있습니다.  
  
 파일에서 추가 작업을 수행하기 전에 항상 반환 값을 검사하여 포인터가 NULL인지 여부를 확인하세요. 오류가 발생한 경우 전역 변수 `errno` 가 설정되어 특정 오류 정보를 가져오는 데 사용할 수 있습니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="unicode-support"></a>유니코드 지원  
 `fopen` 은 유니코드 파일 스트림을 지원합니다. 유니코드 파일을 열려면 다음과 같이 `ccs` 에 원하는 인코딩을 지정하는 `fopen`플래그를 전달합니다.  
  
 `FILE *fp = fopen("newfile.txt", "rt+, ccs=encoding");`  
  
 `encoding` 의 허용 값은 `UNICODE`, `UTF-8`및 `UTF-16LE`입니다.  
  
 파일을 유니코드 모드에서 열면 입력 함수는 연 파일에서 읽은 데이터를 `wchar_t`형식으로 저장되는 UTF-16 데이터로 변환합니다. 유니코드 모드에서 연 파일에 쓰는 함수는 UTF-16 데이터가 포함된 버퍼가 `wchar_t`형식으로 저장되는 것으로 예상합니다. 이 파일이 UTF-8로 인코딩되면 UTF-16 데이터는 쓸 때 UTF-8로 변환되고 이 파일의 UTF-8로 인코딩된 내용은 읽을 때 UTF-16으로 변환됩니다. 유니코드 모드에서 홀수 바이트를 읽거나 쓰려고 하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 오류가 발생합니다. 프로그램에 UTF-8로 저장된 데이터를 읽거나 쓰려는 경우 유니코드 모드 대신 텍스트 또는 이진 파일 모드를 사용합니다. 필수 인코딩은 사용자가 변환해야 합니다.  
  
 파일이 이미 있고 읽기 또는 추가용으로 열려 있는 경우 BOM(바이트 순서 표시)(파일에 있는 경우)에 따라 인코딩이 결정됩니다. BOM 인코딩이 `ccs` 플래그에 지정된 인코딩보다 우선합니다. `ccs` 인코딩은 BOM이 없거나 파일이 새 파일인 경우에만 사용됩니다.  
  
> [!NOTE]
>  BOM 검색은 유니코드 모드로 열려 있는 파일 즉, `ccs` 플래그를 전달하여 연 파일에만 적용됩니다.  
  
 다음 표에서는 파일에서 `ccs` 및 BOM에 지정된 다양한 `fopen` 에 사용되는 모드에 대해 간단히 설명합니다.  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs 플래그 및 BOM을 기반으로 사용되는 인코딩  
  
|`ccs` 플래그|BOM이 없거나 새 파일|BOM: UTF-8|BOM: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 유니코드 모드에서 쓰도록 파일을 열면 BOM이 파일에 자동으로 기록됩니다.  
  
 `mode` 가 "`a, ccs=<encoding>`"인 경우 `fopen` 은 먼저 읽기 권한과 쓰기 권한을 모두 사용하여 파일을 열려고 시도합니다. 성공하면 BOM을 읽고 파일에 대한 인코딩을 결정하고, 실패하면 파일에 대한 기본 인코딩을 사용합니다. 어느 경우든 `fopen` 은 쓰기 전용 권한을 사용하여 파일을 다시 엽니다. 이는 `a` 모드에만 적용되고 `a+` 모드에는 적용되지 않습니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen`|`fopen`|`fopen`|`_wfopen`|  
  
 `mode` 문자열은 다음과 같이 파일에 대해 요청되는 액세스 종류를 지정합니다.  
  
 `"r"`  
 읽기 위해 엽니다. 파일이 없거나 찾을 수 없는 경우 `fopen` 호출이 실패합니다.  
  
 `"w"`  
 쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다.  
  
 `"a"`  
 새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다.  
  
 `"r+"`  
 읽고 쓰기 위해 엽니다. 파일이 있어야 합니다.  
  
 `"w+"`  
 읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다.  
  
 `"a+"`  
 읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다.  
  
 `"a"` 또는 `"a+"` 액세스 형식을 사용하여 파일을 연 경우 모든 쓰기 작업은 파일의 끝에서 수행됩니다. `fseek` 또는 `rewind`를 사용하여 파일 포인터의 위치를 변경할 수 있지만, 파일 포인터는 쓰기 작업을 수행하기 전에 항상 파일 끝으로 다시 이동합니다. 따라서 기존 데이터를 덮어쓸 수 없습니다.  
  
 `"a"` 모드에서는 파일에 추가하기 전에 EOF 표식을 제거하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. `"a+"` 모드에서는 파일에 추가하기 전에 EOF 표식을 제거합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. `"a+"` 모드에서는 Ctrl+Z EOF 표식으로 종료되는 스트림 파일에 추가해야 합니다.  
  
 `"r+"`, `"w+"`또는 `"a+"` 액세스 형식을 지정한 경우 읽기와 쓰기를 모두 사용할 수 있습니다. 즉, 파일이 "업데이트"용으로 열립니다. 하지만 읽기에서 쓰기로 전환할 경우 입력 작업 시 EOF 표식이 필요합니다. EOF가 없는 경우 사이에 파일 위치 지정 함수를 호출해야 합니다. 파일 위치 지정 함수는 `fsetpos`, `fseek`및 `rewind`입니다. 쓰기에서 읽기로 전환할 경우 사이에 `fflush` 또는 파일 위치 지정 함수를 호출해야 합니다.  
  
 이전 값 이외에 다음 문자를 `mode` 에 추가하여 줄 바꿈 문자에 대한 변환 모드를 지정할 수 있습니다.  
  
 `t`  
 텍스트(변환됨) 모드에서 엽니다. 이 모드에서 Ctrl+Z는 입력에서 EOF 문자로 해석됩니다. `"a+"`를 사용하여 읽기/쓰기를 위해 연 파일에서 `fopen` 은 파일 끝에서 Ctrl+Z를 확인하여 제거합니다(가능한 경우). `fseek` 및 `ftell` 을 사용하여 Ctrl+Z로 끝나는 파일 내에서 이동하면 파일의 끝 부분에서 `fseek` 가 제대로 동작하지 않을 수 있으므로 이 작업을 수행합니다.  
  
 텍스트 모드에서 캐리지 리턴-줄 바꿈 조합은 입력 시 단일 줄 바꿈으로 변환 되 고 줄 바꿈 문자는 출력에서 캐리지 리턴-줄 바꿈 조합으로 변환 합니다. 유니코드 스트림 I/O 함수가 텍스트 모드에서 작동할 경우(기본값) 소스 또는 대상 스트림은 멀티바이트 문자 시퀀스로 간주됩니다. 따라서 유니코드 스트림 입력 함수는 멀티바이트 문자를 와이드 문자로 변환합니다( `mbtowc` 함수를 호출한 것으로 간주). 마찬가지로 유니코드 스트림 출력 함수는 와이드 문자를 멀티바이트 문자로 변환합니다( `wctomb` 함수를 호출한 것으로 간주).  
  
 `b`  
 이진(변환되지 않음) 모드에서 엽니다. 캐리지 리턴 및 줄 바꿈 문자를 포함하는 변환은 표시되지 않습니다.  
  
 `t` 또는 `b` 가 `mode`에 지정되지 않은 경우, 기본 변환 모드는 전역 변수 [_fmode](../../c-runtime-library/fmode.md)로 정의됩니다. `t` 또는 `b` 가 인수에 접두어로 추가되면 이 함수는 실행되지 못하고 `NULL`을 반환합니다.  
  
 유니코드 및 멀티바이트 스트림 I/O에서 텍스트 모드 및 이진 모드를 사용하는 방법에 대한 자세한 내용은 [Text and Binary Mode File I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.  
  
 `c`  
 `filename` 또는 `fflush` 을 호출하면 파일 버퍼의 내용이 디스크에 직접 기록되도록 연결된 `_flushall` 에 대한 커밋 플래그를 사용합니다.  
  
 `n`  
 연결된 `filename` 에 대한 커밋 플래그를 "커밋 안 함"으로 다시 설정합니다. 이 값이 기본값입니다. 또한 프로그램을 COMMODE.OBJ와 연결할 경우 전역 커밋 플래그를 재정의합니다. 프로그램을 COMMODE.OBJ와 명시적으로 연결하지 않을 경우 전역 커밋 플래그 기본값은 "커밋 안 함"입니다( [Link Options](../../c-runtime-library/link-options.md)참조).  
  
 `N`  
 자식 프로세스에서 파일을 상속하지 않도록 지정합니다.  
  
 `S`  
 캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다.  
  
 `R`  
 캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다.  
  
 `T`  
 파일을 임시 파일로 지정합니다. 가능하면 디스크에 플러시되지 않습니다.  
  
 `D`  
 파일을 임시 파일로 지정합니다. 마지막 파일 포인터를 닫을 때 삭제됩니다.  
  
 `ccs=ENCODING`  
 이 파일에 대해 사용할 코딩된 문자 집합(`UTF-8`, `UTF-16LE`또는 `UNICODE`)을 지정합니다. ANSI 인코딩을 원할 경우 지정되지 않은 상태로 둡니다.  
  
 다음과 같이 `mode` 및 `fopen` 에 사용되는 `_fdopen` 문자열에 유효한 문자는 `oflag` _open [및](../../c-runtime-library/reference/open-wopen.md) _sopen [에 사용되는](../../c-runtime-library/reference/sopen-wsopen.md)인수와 일치합니다.  
  
|모든 문자열의 문자|`_open`/`_sopen`에 대해 동일한 `oflag` 값|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND`(일반적으로 `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND`(일반적으로 `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT`)|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY`(일반적으로 `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR`(일반적으로 `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|없음|  
|`n`|없음|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 `rb` 모드를 사용하고, 코드를 이식할 필요가 없으며, 큰 파일의 대부분을 읽어야 하거나, 네트워크 성능이 문제가 되지 않을 경우, 메모리 매핑된 Win32 파일을 옵션으로 사용할지 여부를 고려할 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fopen`|\<stdio.h>|  
|`_wfopen`|\<stdio.h> 또는 \<wchar.h>|  
  
 `_wfopen`는 Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 `c`, `n`, `t`, `S`, `R`, `T`및 `D` `mode` 옵션은 `fopen` 및 `_fdopen` 및 should not be used where ANSI portability is desired.  
  
## <a name="example"></a>예제  
 다음 프로그램은 두 파일을 엽니다.  `fclose` 를 사용하여 첫 번째 파일을 닫고 `_fcloseall` 을 사용하여 나머지 파일을 모두 닫습니다.  
  
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
  
## <a name="example"></a>예제  
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
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)
