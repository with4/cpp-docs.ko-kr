---
title: putc, putwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- putwc
- putc
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
- _puttc
- putwc
- putc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e7df1c7810719092874990286c1b22b7e7ec6faa
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="putc-putwc"></a>putc, putwc
스트림에 문자를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 쓸 문자입니다.  
  
 `stream`  
 **FILE** 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 쓴 문자를 반환합니다. 오류 또는 파일 끝 조건을 나타내기 위해 `putc` 및 `putchar`은 `EOF`을 반환하고 `putwc` 및 `putwchar`은 **WEOF**를 반환합니다. 4개 루틴 모두에 대해 [ferror](../../c-runtime-library/reference/ferror.md) 또는 [feof](../../c-runtime-library/reference/feof.md)를 사용하여 오류 또는 파일 끝을 확인합니다. `stream`에 대해 null 포인터가 전달된 경우에는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `EOF` 또는 **WEOF**를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `putc` 루틴은 현재 위치에서 출력 `stream`에 단일 문자(`c`)를 씁니다. `putc`에는 모든 정수를 전달할 수 있지만 하위 8비트만 기록됩니다. `putchar` 루틴은 **putc(** `c`**, stdout)**와 동일합니다. 각 루틴에 대해 읽기 오류가 발생하는 경우 스트림에 대한 오류 표시기가 설정됩니다. `putc` 및 `putchar`은 각각 `fputc` 및 `_fputchar`와 비슷하지만 함수와 매크로 둘 다로 구현됩니다([함수와 매크로 중 선택](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) 참조). `putwc` 및 `putwchar`은 각각 `putc` 및 `putchar`의 와이드 문자 버전입니다. 스트림이 ANSI 모드에서 열리는 경우 `putwc` 및 `putc`가 동일하게 작동합니다. `putc`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 **_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다. 자세한 내용은 **_putc_nolock, _putwc_nolock**을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`putc`|\<stdio.h>|  
|`putwc`|\<stdio.h> 또는 \<wchar.h>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다. 콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)
