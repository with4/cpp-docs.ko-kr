---
title: "printf, _printf_l, wprintf, _wprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_l"
  - "wprintf"
  - "_wprintf_l"
  - "printf"
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
  - "printf"
  - "_tprintf"
  - "wprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_l 함수"
  - "_tprintf 함수"
  - "_tprintf_l 함수"
  - "_wprintf_l 함수"
  - "서식 있는 텍스트[C++]"
  - "printf 함수"
  - "printf 함수, 형식 사양 필드"
  - "printf 함수, using"
  - "printf_l 함수"
  - "tprintf 함수"
  - "tprintf_l 함수"
  - "wprintf 함수"
  - "wprintf_l 함수"
  - "콘솔에 쓰기"
ms.assetid: 77a854ae-5b48-4865-89f4-f2dc5cf80f52
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# printf, _printf_l, wprintf, _wprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

표준 출력 스트림에 서식이 지정된 출력을 출력합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
int printf(  
   const char *format [,  
   argument]...   
);  
int _printf_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### 매개 변수  
 `format`  
 서식 컨트롤입니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 인쇄된 문자 수를 반환하거나 오류가 발생하면 음수 값을 반환합니다.  `format`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  `argument`에서 **EOF**\(0xFFFF\)가 발생하면 함수가 \-1을 반환합니다.  
  
 `errno` 및 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `printf` 함수는 일련의 문자 및 값을 형식 지정하고 표준 출력 스트림인 `stdout`에 출력합니다.  `format` 문자열 다음에 인수가 나오는 경우 `format` 문자열에 해당 인수에 대한 출력 형식을 결정하는 사양이 포함되어야 합니다.  유형의 대상 `FILE`이 아니라, `printf`가 `stdout`에 출력값을 작성해 주는 경우를 제외하고 `printf`와 [fprint](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)가 동일하게 행동합니다.  
  
 `wprintf`는 `printf`의 와이드 문자 버전이며, `format`은 와이드 문자 문자열입니다.  `wprintf` 및 `printf`는 ANSI 모드에서 스트림이 열린 경우 동일하게 동작합니다.  `printf`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_unicode 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tprintf`|`printf`|`printf`|`wprintf`|  
  
 `format` 인수는 일반 문자, 이스케이프 시퀀스 및 형식 사양\(인수가 `format`을 따를 경우\)으로 구성됩니다.  일반 문자 및 이스케이프 시퀀스는 나타나는 순서대로 `stdout`으로 복사됩니다.  예를 들어, 줄  
  
```  
printf("Line one\n\t\tLine two\n");   
```  
  
 출력을 만듭니다.  
  
```  
Line one  
        Line two  
```  
  
 [서식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)은 항상 백분율 기호\(`%`\)로 시작하며 왼쪽에서 오른쪽으로 읽습니다.  `printf`에서 첫 번째 형식 사양을 발견하면\(있을 경우\) `format` 뒤의 첫 번째 인수 값을 변환하고 그에 따라 출력합니다.  두 번째 서식 사양은 두 번째 인수를 변환하여 출력합니다.  형식 사양보다 많은 인수가 있으면 추가 인수가 무시됩니다.  모든 형식 사양에 충분한 인수가 없는 경우 결과가 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tprintf`|`printf`|`printf`|`wprintf`|  
|`_tprintf_l`|`_printf_l`|`_printf_l`|`_wprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`printf`, `_printf_l`|\<stdio.h\>|  
|`wprintf`, `_wprintf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_printf.c  
// This program uses the printf and wprintf functions  
// to produce formatted output.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char     ch = 'h',   
            *string = "computer";  
   wchar_t  wch = L'w',   
            *wstring = L"Unicode";  
   int      count = -9234;  
   double   fp = 251.7366;  
  
   // Display integers  
   printf( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  "  
           "Unsigned: %u\n",  
           count, count, count, count );  
  
   // Display decimals  
   printf( "Decimal %d as:\n   Hex: %Xh  "  
           "C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   // Display in different radixes  
   printf( "Digits 10 equal:\n   Hex: %i  "  
           "Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   // Display characters  
   printf("Characters in field (1):\n"  
          "%10c%5hc%5C%5lc\n",  
          ch, ch, wch, wch);  
   wprintf(L"Characters in field (2):\n"  
           L"%10C%5hc%5c%5lc\n",  
           ch, ch, wch, wch);  
  
   // Display strings  
   printf("Strings in field (1):\n%25s\n"  
          "%25.4hs\n   %S%25.3ls\n",  
          string, string, wstring, wstring);  
   wprintf(L"Strings in field (2):\n%25S\n"  
           L"%25.4hs\n   %s%25.3ls\n",  
           string, string, wstring, wstring);  
  
   // Display real numbers  
   printf("Real numbers:\n   %f %.2f %e %E\n",  
          fp, fp, fp, fp );  
  
   // Display pointer  
   printf( "\nAddress as:   %p\n", &count);  
}  
```  
  
## 샘플 출력  
  
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
  
Address as:   0012FF3C  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [\_set\_output\_format](../../c-runtime-library/set-output-format.md)