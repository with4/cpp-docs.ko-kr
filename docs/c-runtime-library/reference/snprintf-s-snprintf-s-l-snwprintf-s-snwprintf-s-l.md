---
title: _snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _snprintf_s
- _snprintf_s_l
- _snwprintf_s
- _snwprintf_s_l
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
apitype: DLLExport
f1_keywords:
- _snwprintf_s_l
- _sntprintf_s_l
- snprintf_s_l
- _snprintf_s_l
- _sntprintf_s
- _snprintf_s
- snprintf_s
- _snwprintf_s
- snwprintf_s_l
- snwprintf_s
- sntprintf_s
- sntprintf_s_l
dev_langs:
- C++
helpviewer_keywords:
- _snprintf_s_l function
- _snwprintf_s_l function
- _sntprintf_s_l function
- snwprintf_s_l function
- snprintf_s function
- _snprintf_s function
- snprintf_s_l function
- _sntprintf_s function
- sntprintf_s_l function
- sntprintf_s function
- snwprintf_s function
- _snwprintf_s function
- formatted text [C++]
ms.assetid: 9336ab86-13e5-4a29-a3cd-074adfee6891
caps.latest.revision: 32
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8a3e2cd1a9bff5c7cb08e30753e98b1769e0b7fa
ms.lasthandoff: 02/24/2017

---
# <a name="snprintfs-snprintfsl-snwprintfs-snwprintfsl"></a>_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l
문자열에 서식이 지정된 데이터를 씁니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _snprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf_s(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_s(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 출력을 위한 저장소 위치입니다.  
  
 `sizeOfBuffer`  
 출력을 위한 저장소 위치의 크기입니다. `_snprintf_s`의 경우 `bytes` 단위 크기이고 `_snwprintf_s`의 경우 `words` 단위 크기입니다.  
  
 `Count`  
 저장할 최대 문자 수 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)입니다.  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `_snprintf_s`는 종료 null 문자를 제외하고 `buffer`에 저장된 문자 수를 반환합니다. `_snwprintf_s`는 종료 null 와이드 문자를 제외하고 `buffer`에 저장된 와이드 문자 수를 반환합니다.  
  
 데이터와 종료 null을 저장하는 데 필요한 저장소가 `sizeOfBuffer`를 초과하는 경우에는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 잘못된 매개 변수 처리기가 호출된 후에 실행을 계속하면 이러한 함수는 `buffer`를 빈 문자열로 설정하고 `errno`를 `ERANGE`로 설정한 후에 -1을 반환합니다.  
  
 `buffer` 또는 `format`이 `NULL` 포인터이거나 `count`가&0;보다 작거나 같으면 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_snprintf_s` 함수는 `buffer`에서 `count` 이하의 문자 서식을 지정하고 해당 문자를 저장한 다음 종료 null을 추가합니다. 각 인수(있는 경우)는 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다. 형식은 `printf` 함수 패밀리와 일치합니다. [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)를 참조하세요. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 `count`가 [_TRUNCATE](../../c-runtime-library/truncate.md)이면 `_snprintf_s`는 종료 null을 위한 공간을 남겨 두고 `buffer`에 포함될 수 있는 만큼의 문자열을 작성합니다. 종료 null을 포함한 전체 문자열을 `buffer`에 포함할 수 있으면 `_snprintf_s`는 종료 null을 포함하지 않고 작성된 문자 수를 반환합니다. 그렇지 않으면 `_snprintf_s`는 자르기가 수행되었음을 나타내는 -1을 반환합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  
  
 `_snwprintf_s`는 `_snprintf_s`의 와이드 문자 버전이며, `_snwprintf_s`에 대한 포인터 인수는 와이드 문자 문자열입니다. `_snwprintf_s`에서 인코딩 오류의 탐지 방식은 `_snprintf_s`에서와 다를 수 있습니다. `_snwprintf_s`는 `swprintf_s`와 마찬가지로 `FILE` 형식의 대상이 아닌 문자열에 출력을 씁니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_sntprintf_s`|`_snprintf_s`|`_snprintf_s`|`_snwprintf_s`|  
|`_sntprintf_s_l`|`_snprintf_s_l`|`_snprintf_s_l`|`_snwprintf_s_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_snprintf_s`, `_snprintf_s_l`|\<stdio.h>|  
|`_snwprintf_s`, `_snwprintf_s_l`|\<stdio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_snprintf_s.cpp  
// compile with: /MTd  
  
// These #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
int snprintf_s_tester( const char * fmt, int x, size_t count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "%zd-byte buffer; truncation semantics\n",  
               _countof(dest) );  
   else  
      printf( "count = %zd; %zd-byte buffer\n",  
               count, _countof(dest) );  
  
   int ret = _snprintf_s( dest, _countof(dest), count, fmt, x );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return ret;  
}  
  
void Examples()  
{  
   // formatted output string is 9 characters long: "<<<123>>>"  
   snprintf_s_tester( "<<<%d>>>", 121, 8 );  
   snprintf_s_tester( "<<<%d>>>", 121, 9 );  
   snprintf_s_tester( "<<<%d>>>", 121, 10 );  
  
   printf( "\nDestination buffer too small:\n" );  
  
   snprintf_s_tester( "<<<%d>>>", 1221, 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   int ret = snprintf_s_tester( "<<<%d>>>", 1221, _TRUNCATE );  
   printf( "    truncation %s occur\n", ret == -1 ? "did"  
                                                  : "did not" );  
  
   ret = snprintf_s_tester( "<<<%d>>>", 121, _TRUNCATE );  
   printf( "    truncation %s occur\n", ret == -1 ? "did"  
                                                  : "did not" );  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   _snprintf( dest, 10, "<<<%d>>>", 12321 );  
   // With secure template overloads enabled (see #defines  
   // at top of file), the preceding line is replaced by  
   //    _snprintf_s( dest, _countof(dest), 10, "<<<%d>>>", 12345 );  
   // Instead of causing a buffer overrun, _snprintf_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, _snprintf would  
   // write 10 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
```Output  
  
count = 8; 10-byte buffer  
    new contents of dest: '<<<121>>'  
  
count = 9; 10-byte buffer  
    new contents of dest: '<<<121>>>'  
  
count = 10; 10-byte buffer  
    new contents of dest: '<<<121>>>'  
  
Destination buffer too small:  
  
count = 10; 10-byte buffer  
Invalid parameter handler invoked: ("Buffer too small", 0)  
    new contents of dest: ''  
  
Truncation examples:  
  
10-byte buffer; truncation semantics  
    new contents of dest: '<<<1221>>'  
    truncation did occur  
  
10-byte buffer; truncation semantics  
    new contents of dest: '<<<121>>>'  
    truncation did not occur  
  
Secure template overload example:  
Invalid parameter handler invoked: ("Buffer too small", 0)  
    new contents of dest: ''  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)
