---
title: printf_s, _printf_s_l, wprintf_s, _wprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _printf_s_l
- wprintf_s
- _wprintf_s_l
- printf_s
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
- wprintf_s
- printf_s
dev_langs:
- C++
helpviewer_keywords:
- wprintf_s function
- tprintf_s function
- _tprintf_s function
- printf_s_l function
- printf_s function
- _printf_s_l function
- printf function, format specification fields
- printf function, using
- _tprintf_s_l function
- wprintf_s_l function
- formatted text [C++]
- tprintf_s_l function
- _wprintf_s_l function
ms.assetid: 044ebb2e-5cc1-445d-bb4c-f084b405615b
caps.latest.revision: 21
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
ms.openlocfilehash: 008ecd864959078951a3671a318abfa6e593bd49
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="printfs-printfsl-wprintfs-wprintfsl"></a>printf_s, _printf_s_l, wprintf_s, _wprintf_s_l
서식이 지정된 출력을 표준 출력 스트림에 인쇄합니다. 이러한 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 버전에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
int printf_s(  
   const char *format [,  
   argument]...   
);  
int _printf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `format`  
 컨트롤의 서식을 지정합니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 인쇄된 문자 수 또는 오류가 발생하는 경우 음수 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `printf_s` 함수는 일련의 문자와 값의 서식을 지정하여 표준 출력 스트림 `stdout`에 인쇄합니다. 인수가 *format* 문자열 다음에 나오는 경우 `format` 문자열에 해당 인수에 대한 출력 형식을 결정하는 지정이 포함되어야 합니다.  
  
 `printf_s`와 `printf` 간의 주요 차이점은 `printf_s`가 올바른 형식 지정 문자에 대한 형식 문자열을 검사하는 반면 `printf`는 형식 문자열이 null 포인터인지 여부만 검사한다는 점입니다. 검사에 실패할 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 함수는 -1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 `errno` 및 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 `printf_s`및 `fprintf_s` 점을 제외 하 고 동일 하 게 작동 `printf_s` 출력을 씁니다 `stdout` 형식의 대상이 아니라 `FILE`합니다. 자세한 내용은 [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)를 참조하세요.  
  
 `wprintf_s`는 `printf_s`의 와이드 문자 버전이며 `format`은 와이드 문자열입니다. 스트림이 ANSI 모드에서 열리는 경우 `wprintf_s` 및 `printf_s`가 동일하게 작동합니다. `printf_s`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tprintf_s`|`printf_s`|`printf_s`|`wprintf_s`|  
|`_tprintf_s_l`|`_printf_s_l`|`_printf_s_l`|`_wprintf_s_l`|  
  
 `format` 인수는 일반 문자, 이스케이프 시퀀스 및 형식 지정(인수가 `format` 뒤에 오는 경우)으로 구성됩니다. 일반 문자 및 이스케이프 시퀀스는 표시되는 순서대로 `stdout`에 복사됩니다. 예를 들어, 다음 줄에서  
  
```  
printf_s("Line one\n\t\tLine two\n");   
```  
  
 는 출력을 생성합니다.  
  
```  
Line one  
        Line two  
```  
  
 [형식 지정](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)은 항상 백분율 기호(`%`)로 시작되며 왼쪽에서 오른쪽으로 설정됩니다. `printf_s`는 첫 번째 형식 지정(있는 경우)을 발견하면 `format` 다음의 첫 번째 인수 값을 변환하여 적절하게 출력합니다. 두 번째 형식 지정이 있으면 두 번째 인수가 변환되는 출력되는 식으로 실행이 계속됩니다. 형식 지정보다 인수가 더 많으면 추가 인수는 무시됩니다. 모든 형식 지정에 해당하는 충분한 인수가 없으면 결과는 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `format` 이 사용자 정의 문자열이 아닌지 확인하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`printf_s`, `_printf_s_l`|\<stdio.h>|  
|`wprintf_s`, `_wprintf_s_l`|\<stdio.h> 또는 \<wchar.h>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다. 콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_printf_s.c  
/* This program uses the printf_s and wprintf_s functions  
 * to produce formatted output.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   char   ch = 'h', *string = "computer";  
   int    count = -9234;  
   double fp = 251.7366;  
   wchar_t wch = L'w', *wstring = L"Unicode";  
  
   /* Display integers. */  
   printf_s( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  Unsigned: %u\n",  
           count, count, count );  
  
   printf_s( "Decimal %d as:\n   Hex: %Xh  C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   /* Display in different radixes. */  
   printf_s( "Digits 10 equal:\n   Hex: %i  Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   /* Display characters. */  
  
   printf_s("Characters in field (1):\n%10c%5hc%5C%5lc\n", ch, ch, wch, wch);  
   wprintf_s(L"Characters in field (2):\n%10C%5hc%5c%5lc\n", ch, ch, wch, wch);  
  
   /* Display strings. */  
  
   printf_s("Strings in field (1):\n%25s\n%25.4hs\n   %S%25.3ls\n",  
   string, string, wstring, wstring);  
   wprintf_s(L"Strings in field (2):\n%25S\n%25.4hs\n   %s%25.3ls\n",  
       string, string, wstring, wstring);  
  
   /* Display real numbers. */  
   printf_s( "Real numbers:\n   %f %.2f %e %E\n", fp, fp, fp, fp );  
  
   /* Display pointer. */  
   printf_s( "\nAddress as:   %p\n", &count);  
  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Integer formats:  
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062  
Decimal -9234 as:  
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756  
Digits 10 equal:  
   Hex: 16  Octal: 8  Decimal: 10  
Characters in field (1):  
         h    h    w    w  
Characters in field (2):  
         h    h    w    w  
Strings in field (1):  
                 computer  
                     comp  
   Unicode                      Uni  
Strings in field (2):  
                 computer  
                     comp  
   Unicode                      Uni  
Real numbers:  
   251.736600 251.74 2.517366e+002 2.517366E+002  
  
Address as:   0012FF78  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)
