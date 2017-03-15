---
title: "_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_p"
  - "_wprintf_p"
  - "_printf_p_l"
  - "_wprintf_p_l"
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
  - "wprintf_p"
  - "_wprintf_p"
  - "printf_p_l"
  - "_printf_p"
  - "printf_p"
  - "_wprintf_p_l"
  - "_printf_p_l"
  - "wprintf_p_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_p 함수"
  - "_printf_p_l 함수"
  - "_tprintf_p_l 함수"
  - "_wprintf_p 함수"
  - "_wprintf_p_l 함수"
  - "printf_p 함수"
  - "printf_p_l 함수"
  - "tprintf_p_l 함수"
  - "wprintf_p 함수"
  - "wprintf_p_l 함수"
ms.assetid: 1b7e9ef9-a069-45db-af9d-c2730168322e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인쇄는 표춘 출력 스트림에서 출력이 형식화되고 형식 문자열에서 사용되곤하는 매개변수 순서를 지정할 수 있도록 합니다.  
  
## 구문  
  
```  
int _printf_p(  
   const char *format [,  
   argument]...   
);  
int _printf_p_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int _wprintf_p(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_p_l(  
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
 인쇄된 문자 수를 반환하거나 오류가 발생하면 음수 값을 반환합니다.  
  
## 설명  
 `_printf_p` 함수는 일련의 문자 및 값을 형식 지정하고 표준 출력 스트림인 `stdout`에 출력합니다.  `format` 문자열 다음에 인수가 나오는 경우 `format` 문자열에 해당 인수에 대한 출력 형식을 결정하는 사양이 포함되어야 합니다. \(다음링크를 참조하십시오 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)\).  
  
 `_printf_p` 및 `printf_s` 의 다른 점은 `_printf_p` 가 지원 위치 매개 변수를 지원하는 것입니다. 이는 형식 문자열에서 사용되는 인수의 사용 되는 순서를 지정하는것입니다.  자세한 내용은 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)을 참조하십시오.  
  
 `_wprintf_p` 와이드 문자 버전인 `_printf_p` ;마치 동일한 스트림에서 ANSI 모드에서 열리는 경우입니다.  `_printf_p` 는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  
  
 만약 `format` 또는 `argument` 가 `NULL`일 경우, `_printf_p` 와 `_wprintf_p` 함수는 잘못된 매개변수 처리기를 호출합니다. 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 자세히 설명되어 있습니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tprintf_p`|`_printf_p`|`_printf_p`|`_wprintf_p`|  
|`_tprintf_p_l`|`_printf_p_l`|`_printf_p_l`|`_wprintf_p_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_printf_p`, `_printf_p_l`|\<stdio.h\>|  
|`_wprintf_p`, `_wprintf_p_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_printf_p.c  
// This program uses the _printf_p and _wprintf_p  
// functions to choose the order in which parameters  
// are used.  
  
#include <stdio.h>  
  
int main( void )  
{  
   // Positional arguments   
   _printf_p( "Specifying the order: %2$s %3$s %1$s %4$s %5$s.\n",  
              "little", "I'm", "a", "tea", "pot");  
  
   // Resume arguments  
   _wprintf_p( L"Reusing arguments: %1$d %1$d %1$d %1$d\n", 10);  
  
   // Width argument  
   _printf_p("Width specifiers: %1$*2$s", "Hello\n", 10);  
}  
```  
  
  **순서 지정: 저는 작은 차 항아리입니다.**  
**인수 전달**  
**너비 지정자: Hello**   
## 해당 .NET Framework 항목  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)