---
title: "wcrtomb | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcrtomb"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcrtomb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "문자, 변환"
  - "멀티바이트 문자"
  - "wcrtomb 함수"
  - "와이드 문자, 변환"
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcrtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자는 이것의 멀티 바이트 문자 표현으로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `mbchar`  
 결과 멀티 바이트를 문자로 변환합니다.  
  
 \[in\] `wchar`  
 변환할 와이드 문자입니다.  
  
 \[in\] `mbstate`  
 이 `mbstate_t` 개체에 대한 포인터입니다.  
  
## 반환 값  
 변환된 멀티 바이트 문자의 나타나는 데에 필요한 바이트 수를 반환합니다. 그렇지 않고 오류가 발생하는 경우 \-1을 반환합니다.  
  
## 설명  
 `wcrtomb` 함수는 `mbstate` 을 포함한 지정된 변환 상태에서의 시작하여, `wchar` 에서 포함된 값으로부터, `mbchar` 로 표현되는 주소로 와이드 문자를 반환합니다.  반환 값은 상응하는 멀티 바이트 문자를 표현하는 데에 필요한 바이트 수입니다. 그러나 `MB_CUR_MAX` 바이트 이상은 반환되지 않습니다.  
  
 `mbstate`이 null인 경우, `mbchar`의 변환 상태를 포함하는 내부의 `mbstate_t` 개체가 사용됩니다.  만일 문자 시퀀스인 `wchar` 가 멀티바이트 문자 표시에 반응하지 않는다면, \-1 이 반환되고 `errno` 는 `EILSEQ` 으로 설정됩니다.  
  
 이 `wcrtomb` 함수는 재시작 가능성이라는 면에서 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) 와 다릅니다.  변환 상태는 동일한 것들의 차후의 호출 또는 다른 재시작 되는 함수를 위해 `mbstate` 에 저장됩니다.  재시작 함수나 그렇지 않은 함수의 사용을 혼용할 때, 결과는 정의되지 않습니다.  예를 들어, `wcstombs` 대신 `wcsrtombs` 이 사용되었다면, 응용 프로그램은 `wcsnlen` 보다 `wcsrlen` 을 사용합니다.  
  
 C\+\+에서, 이러한 함수는 최신의 보안 대응 함수를 호출하는 탬플릿 오버로드입니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 예외  
 이 `wcrtomb` 함수는 현재 스레드에서 `setlocale` 를 실행하는 동안 호출하는 함수가 필요없는 안전한 멀티 스레드 입니다. 이 함수가 실행 중이며 `mbstate` 이 null인 경우입니다.  
  
## 예제  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
  **해당 와이드 문자 "Q"는 "Q" 멀티 바이트 문자로 변환됩니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wcrtomb`|\<wchar.h\>|  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)