---
title: ungetc, ungetwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
dev_langs:
- C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 3bab0bd81a8a17fd32c244bab0dd30658564d257
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc
스트림에 문자를 다시 푸시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 푸시할 문자 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 이러한 각 함수 반환 문자 인수 `c`합니다. `c`를 다시 푸시할 수 없거나 읽은 문자가 없는 경우에는 입력 스트림이 변경되지 않으며 `ungetc`는 `EOF`를 반환하고 `ungetwc`는 `WEOF`를 반환합니다. `stream`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `EOF` 또는 `WEOF`가 반환되고 `errno`는 `EINVAL`로 설정됩니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `ungetc` 함수는 `c` 문자를 `stream`에 다시 푸시하고 파일 끝 표시기를 지웁니다. 이때 스트림이 읽기를 위해 열려 있어야 합니다. 후속 작업에서 읽기 `stream` 로 시작 `c`합니다. `ungetc`를 사용하여 스트림에 `EOF`를 푸시하려는 시도는 무시됩니다.  
  
 `ungetc`에 의해 스트림에 배치되는 문자는 스트림에서 해당 문자를 읽기 전에 `fflush`, `fseek`, `fsetpos` 또는 `rewind`를 호출하는 경우 지워질 수 있습니다. 파일 위치 표시기에는 문자가 다시 푸시되기 전의 값이 지정됩니다. 스트림에 해당하는 외부 저장소는 변경되지 않습니다. 텍스트 스트림에 대해 `ungetc`가 정상적으로 호출되어도 다시 푸시된 모든 문자를 읽거나 삭제할 때까지 파일 위치 표시기는 지정되지 않습니다. 이진 스트림에 대해 각 `ungetc`를 정상적으로 호출하면 파일 위치 표시기가 감소합니다. 호출 전에 표시기의 값이 0이었다면 호출 후에는 값이 정의되지 않습니다.  
  
 두 호출 사이에 읽기 또는 파일 배치 작업이 수행되지 않은 상태로 `ungetc`를 두 번 호출하는 경우의 결과는 예측할 수 없습니다. `fscanf`를 호출한 후에 `ungetc`를 호출하면 `getc` 등의 다른 읽기 작업이 수행되지 않은 경우 호출이 실패할 수 있습니다. `fscanf` 자체가 `ungetc`를 호출하기 때문입니다.  
  
 `ungetwc`는 `ungetc`의 와이드 문자 버전입니다. 그러나 텍스트 또는 이진 스트림에 대해 각 `ungetwc`가 정상적으로 호출되어도 다시 푸시된 모든 문자를 읽거나 삭제할 때까지 파일 위치 표시기는 지정되지 않습니다.  
  
 이러한 함수는 스레드로부터 안전하며, 실행 중에 중요한 데이터를 잠급니다. 데이터를 잠그지 않는 버전은 [_ungetc_nolock, _ungetwc_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`ungetc`|\<stdio.h>|  
|`ungetwc`|\<stdio.h> 또는 \<wchar.h>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다. 콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
```Output  
  
      521aNumber = 521  
Next character in stream = 'a'  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)
