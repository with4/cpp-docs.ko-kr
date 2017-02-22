---
title: "_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snprintf_s"
  - "_snprintf_s_l"
  - "_snwprintf_s"
  - "_snwprintf_s_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_snwprintf_s_l"
  - "_sntprintf_s_l"
  - "snprintf_s_l"
  - "_snprintf_s_l"
  - "_sntprintf_s"
  - "_snprintf_s"
  - "snprintf_s"
  - "_snwprintf_s"
  - "snwprintf_s_l"
  - "snwprintf_s"
  - "sntprintf_s"
  - "sntprintf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_snprintf_s 함수"
  - "_snprintf_s_l 함수"
  - "_sntprintf_s 함수"
  - "_sntprintf_s_l 함수"
  - "_snwprintf_s 함수"
  - "_snwprintf_s_l 함수"
  - "서식 있는 텍스트[C++]"
  - "snprintf_s 함수"
  - "snprintf_s_l 함수"
  - "sntprintf_s 함수"
  - "sntprintf_s_l 함수"
  - "snwprintf_s 함수"
  - "snwprintf_s_l 함수"
ms.assetid: 9336ab86-13e5-4a29-a3cd-074adfee6891
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# _snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에 서식이 지정된 데이터를 씁니다. 이 버전의 [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치입니다.  
  
 `sizeOfBuffer`  
 출력에 대 한 저장소 위치의 크기입니다. 크기 조정에 `bytes` 에 대 한 `_snprintf_s` 크기 또는 `words` 에 대 한 `_snwprintf_s`합니다.  
  
 `Count`  
 최대 문자를 저장, 또는 [\_TRUNCATE](../../c-runtime-library/truncate.md)합니다.  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_snprintf_s` 에 저장 된 문자 수를 반환 `buffer`, null 종결 문자를 제외 합니다.`_snwprintf_s`는 종료 null 와이드 문자를 제외하고 `buffer`에 저장된 와이드 문자 수를 반환합니다.  
  
 종료 null와 데이터를 저장 하는 데 필요한 저장소 초과 하는 경우 `sizeOfBuffer`, 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이러한 함수를 잘못 된 매개 변수 처리기 후 실행 계속 하는 경우 설정 `buffer` 을 빈 문자열로 설정 `errno` 를 `ERANGE`, \-1을 반환 하 고 있습니다.  
  
 경우 `buffer` 또는 `format` 는 `NULL` 포인터 또는 `count` 값 보다 작거나 0으로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  
  
 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `_snprintf_s` 함수 형식 및 저장소 `count` 자 미만의 문자 `buffer` 종료 null을 추가 합니다. 각 인수 \(있는 경우\) 변환 되 고 해당 형식 사양에 따라 출력 `format`합니다. 형식은 일치는 `printf` 함수 패밀리를; 참조 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
 경우 `count` 은 [\_TRUNCATE](../../c-runtime-library/truncate.md), 다음 `_snprintf_s` 쓰기 수 있는 만큼 문자열의 크기에 맞게 `buffer` 종료 null에 대 한 공간을 두고 있습니다. 종결 null\) \(포함 된 전체 문자열에 포함 되 면 `buffer`, 다음 `_snprintf_s` \(종료 null 포함 안 함\)에 기록 된; 문자 수를 반환 그렇지 `_snprintf_s` 잘림이 나타내는\-1을 반환 합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  
  
 `_snwprintf_s`는 `_snprintf_s`의 와이드 문자 버전이며, `_snwprintf_s`에 대한 포인터 인수는 와이드 문자 문자열입니다.`_snwprintf_s`에서 인코딩 오류의 탐지 방식은 `_snprintf_s`에서와 다를 수 있습니다.`_snwprintf_s`, 같은 `swprintf_s`, 를 유형의 대상 대신 문자열에 출력을 기록 `FILE`합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_sntprintf_s`|`_snprintf_s`|`_snprintf_s`|`_snwprintf_s`|  
|`_sntprintf_s_l`|`_snprintf_s_l`|`_snprintf_s_l`|`_snwprintf_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_snprintf_s`, `_snprintf_s_l`|\<stdio.h\>|  
|`_snwprintf_s`, `_snwprintf_s_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 예제  
  
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
  
count = 8; 대상의 새 내용을 10 바이트 버퍼: ' <<< 121 >> ' count = 9; 대상의 새 내용을 10 바이트 버퍼: '<<< 121 >>> ' count = 10; 10 바이트 버퍼 대상의 새 내용을: '<<< 121 >>> ' 대상 버퍼가 너무 작습니다: count = 10; 10 바이트 버퍼 잘못 된 매개 변수 처리기가 호출: ("버퍼가 너무 작습니다.", 0) 대상의 새 내용을: ' 잘림 예제: 10 바이트 버퍼입니다. 대상의 잘림 의미 체계 새로운 내용을: ' <<< 1221 >> ' 잘릴 않았습니다 10 바이트 버퍼입니다. 대상의 잘림 의미 체계 새로운 내용을: '<<< 121 >>> ' 잘림 안전한 템플릿 오버 로드 예제 발생 하지 않았습니다: 잘못 된 매개 변수 처리기를 호출: ("버퍼가 너무 작습니다.", 0) 대상의 새 내용을: '  
```  
  
## 해당 .NET Framework 항목  
 적용할 수 없음 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)