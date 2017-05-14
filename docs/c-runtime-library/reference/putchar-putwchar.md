---
title: putchar, putwchar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- putchar
- putwchar
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
- putchar
- putwchar
- _puttchar
dev_langs:
- C++
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
caps.latest.revision: 12
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
ms.openlocfilehash: 1d1cf554b7d359c3bd761656df60881c4be514b8
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="putchar-putwchar"></a>putchar, putwchar
**stdout**에 문자를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int putchar(  
   int c   
);  
wint_t putwchar(  
   wchar_t c   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 쓸 문자입니다.  
  
## <a name="return-value"></a>반환 값  
 쓴 문자를 반환합니다. 오류 또는 파일 끝 조건을 나타내기 위해 `putc` 및 `putchar`은 `EOF`을 반환하고 `putwc` 및 `putwchar`은 **WEOF**를 반환합니다. 4개 루틴 모두에 대해 [ferror](../../c-runtime-library/reference/ferror.md) 또는 [feof](../../c-runtime-library/reference/feof.md)를 사용하여 오류 또는 파일 끝을 확인합니다. `stream`에 대해 null 포인터가 전달된 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 예외를 생성합니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `EOF` 또는 **WEOF**를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `putc` 루틴은 현재 위치에서 출력 `stream`에 단일 문자(`c`)를 씁니다. `putc`에는 모든 정수를 전달할 수 있지만 하위 8비트만 기록됩니다. `putchar` 루틴은 **putc(** `c`**, stdout)**와 동일합니다. 각 루틴에 대해 읽기 오류가 발생하는 경우 스트림에 대한 오류 표시기가 설정됩니다. `putc` 및 `putchar`은 각각 `fputc` 및 `_fputchar`와 비슷하지만 함수와 매크로 둘 다로 구현됩니다([함수와 매크로 중 선택](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) 참조). `putwc` 및 `putwchar`은 각각 `putc` 및 `putchar`의 와이드 문자 버전입니다.  
  
 **_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다. 이러한 버전에서는 다른 스레드를 잠그는 오버헤드가 발생하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttchar`|`putchar`|`putchar`|**putwchar**|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`putchar`|\<stdio.h>|  
|`putwchar`|\<stdio.h> 또는 \<wchar.h>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다. 콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_putchar.c  
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
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putchar( *p );  
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
