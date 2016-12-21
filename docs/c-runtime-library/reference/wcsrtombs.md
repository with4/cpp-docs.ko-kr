---
title: "wcsrtombs | Microsoft Docs"
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
  - "wcsrtombs"
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
  - "wcsrtombs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcsrtombs 함수"
  - "문자열 변환, 와이드 문자"
  - "와이드 문자, 문자열"
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcsrtombs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자 문자열을 멀티 바이트 문자 문자열 표현으로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [wcsrtombs\_s](../../c-runtime-library/reference/wcsrtombs-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `mbstr`  
 그 결과는 멀티바이트 문자 문자열의 주소 위치를 변환합니다.  
  
 \[in\] `wcstr`  
 와이드 문자 문자열 변환의 위치를 간접적으로 가리킵니다.  
  
 \[in\] `count`  
 변환할 문자의 수 입니다.  
  
 \[in\] `mbstate`  
 `mbstate_t` 변환 상태 개체에 대한 포인터입니다.  
  
## 반환 값  
 성공적으로 변환된 바이트의 수를 반환합니다, 이 때, null 바이트\(있는 경우\)를 종료시킨 null 값을 포함하지 않습니다. 그렇지 않을 경우 오류가 발생하고 \-1을 포함하지 않습니다.  
  
## 설명  
 `wcsrtombs` 함수는 와이드 문자의 문자열을 반환합니다, `mbstate` 를 포함하는 특정한 변환 상태에서 시작합니다, `wcstr` 에서 간접적으로 가리킨 값에서 `mbstr` 의 주소값까지 입니다.  와이드 문자가 종료될때까지 각 문자열을 계속 변환합니다. 이는 반응 없는 문자열이 생기거나 다음 문자가 `count` 를 포함하는 한계를 초과할 때까지입니다.  `wcsrtombs` 이 `count` 가 발생할 때나 그 이 전에 와이드 null문자\(L'\\0'\)를 발견한다면, 이것은 8비트 0으로 변환하고 멈춥니다.  
  
 따라서 멀티 바이트 문자 문자열에서 `mbstr` 는 null로 끝나는 경우에 `wcsrtombs` 와이드 null 문자로 변환 하는 동안 발생 합니다.  만일 `wcstr` 와 `mbstr` 에 의해 가르켜진 시퀀스가 겹쳐질 경우, `wcsrtombs` 의 동작은 정의되지 않습니다.  `wcsrtombs` 는 현재 로캘의 LC\_TYPE 범주에 의해 영향이 미칩니다.  
  
 이 `wcsrtombs` 함수는 재시작 가능성이라는 면에서 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) 와 다릅니다.  변환 상태는 동일한 것들의 차후의 호출 또는 다른 재시작 되는 함수를 위해 `mbstate` 에 저장됩니다.  재시작 함수나 그렇지 않은 함수의 사용을 혼용할 때, 결과는 정의되지 않습니다.  예를 들어, `wcstombs` 대신 `wcsrtombs` 이 사용되었다면, 응용 프로그램은 `wcsnlen` 보다 `wcsrlen` 을 사용합니다.  
  
 `mbstr` 인수가 `NULL`이면, `wcsrtombs`은 대상 문자열의 요구 크기를 바이트의 형태로 반환합니다.  만일 `mbstate` 이 null인 경우, 내부적 `mbstate_t` 변환 상태를 사용합니다.  만일 문자 시퀀스인 `wchar` 가 멀티바이트 문자 표시에 반응하지 않는다면, \-1 이 반환되고 `errno` 는 `EILSEQ` 으로 설정됩니다.  
  
 C\+\+에서, 이러한 함수는 최신의 보안 대응 함수를 호출하는 탬플릿 오버로드입니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 예외  
 이 `wcsrtombs` 함수는 현재 스레드에서 `setlocale` 를 실행하는 동안 호출하는 함수가 필요없는 안전한 멀티 스레드 입니다. 이러한 함수는 실행되고 `mbstate` 이 null이 아닐 경우입니다.  
  
## 예제  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
  **문자열이 성공적으로 변환되었습니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wcsrtombs`|\<wchar.h\>|  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)