---
title: "wcrtomb_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcrtomb_s"
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
  - "wcrtomb_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "변환 하는 와이드 문자"
  - "wcrtomb_s 함수"
  - "멀티바이트 문자"
  - "문자를 변환"
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# wcrtomb_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자는 멀티 바이트 문자 표현으로 변환 합니다. 버전의 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `pReturnValue`  
 오류가 발생 하는 경우 쓴 바이트 수 또는\-1을 반환 합니다.  
  
 \[out\] `mbchar`  
 결과 멀티 바이트 문자를 변환 합니다.  
  
 \[in\] `sizeOfmbchar`  
 크기는 `mbchar` 변수 \(바이트\)에서입니다.  
  
 \[in\] `wchar`  
 변환할 와이드 문자입니다.  
  
 \[in\] `mbstate`  
 `mbstate_t` 개체에 대한 포인터입니다.  
  
## 반환 값  
 0 반환 또는 `errno` 오류가 발생 하는 경우의 값입니다.  
  
## 설명  
 `wcrtomb_s` 함수에 포함 된 지정 된 변환 상태에서 시작 하는 와이드 문자 변환 `mbstate`, 에 포함 된 값에서 `wchar`, 를 나타내는 주소에 `mbchar`합니다.`pReturnValue` 값 아니지만 변환 하는 바이트 수가 됩니다 이상 `MB_CUR_MAX` 바이트 또는 오류가 발생 한 경우에\-1입니다.  
  
 경우 `mbstate` 은 null로, 내부 `mbstate_t` 변환 상태가 사용 됩니다. 에 있는 문자가 포함 된 경우 `wchar` 해당 멀티 바이트 문자의 값이 없는 `pReturnValue` \-1 되 고 반환 합니다는 `errno` 값 `EILSEQ`합니다.  
  
 `wcrtomb_s` 함수에서 다른 [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) 해당 재시작 가능성으로 합니다. 같거나 다른 다시 시작 가능 함수에 대한 후속 호출에서는 변환 상태가 `mbstate`에 저장됩니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어, 응용 프로그램 사용 `wcsrlen` 대신 `wcslen`, 후속 호출을 사용 하는 경우, `wcsrtombs_s` 대신 사용 된 `wcstombs_s.`  
  
 C \+ \+에서는이 함수를 사용 하 여 단순화 되어 템플릿 오버 로드 합니다. 오버 로드는 버퍼 길이 자동으로 유추할 수 \(크기 인수를 지정할 필요가 없어짐\) 및를 보다 최신의 보안 대응, 기존의 비보안 함수를 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
## 예외  
 `wcrtomb_s` 함수는 현재 스레드에서 호출 하지으로 아니면 다중 스레드로부터 안전은 `setlocale` 이 함수를 실행 중일 때와 `mbstate` null입니다.  
  
## 예제  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
해당 하는 와이드 문자 "Q"으로 변환 된는 "Q" 멀티 바이트 문자입니다.  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wcrtomb_s`|\<wchar.h\>|  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)