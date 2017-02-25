---
title: "wcsrtombs_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsrtombs_s"
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
  - "wcsrtombs_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문자열 변환, 와이드 문자"
  - "wcsrtombs_s 함수"
  - "와이드 문자, 문자열"
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# wcsrtombs_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자 문자열을 멀티 바이트 문자 문자열 표현으로 변환합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) 버전입니다.  
  
## 구문  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `pReturnValue`  
 변환 된 문자 수입니다.  
  
 \[out\] `mbstr`  
 결과 변환 멀티 바이트 문자열을위한 버퍼의 주소입니다.  
  
 \[out\] `sizeInBytes`  
 바이트에서 `mbstr` 버퍼의 크기입니다.  
  
 \[in\] `wcstr`  
 변환하는 와이드 문자열에 대한 포인터입니다.  
  
 \[in\] `count`  
 `mbstr` 버퍼 또는 [\_TRUNCATE](../../c-runtime-library/truncate.md) 에서 최대 바이트로 저장되어집니다.  
  
 \[in\] `mbstate`  
 `mbstate_t` 전환상태개체에 대한 포인터입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
|오류 조건|반환 값과 `errno`|  
|-----------|-------------------|  
|`mbstr` 는 `NULL` 및 `sizeInBytes` \> 0 입니다.|`EINVAL`|  
|`wcstr`가 `NULL`인 경우|`EINVAL`|  
|대상 버퍼가 너무 작아 변환 된 문자열을 포함할 수 없습니다. \( `count` 가 `_TRUNCATE` 가 아닌 한, 아래 설명 참조\)|`ERANGE`|  
  
 이러한 조건이 발생 하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 설명된 대로 잘못 된 매개 변수 예외를 호출합니다.  실행이 계속 되도록 혀용된 경우, 함수는 오류 코드를 반환하고 `errno` 를 테이블에 표시 된 대로 설정합니다.  
  
## 설명  
 `wcsrtombs_s` 함수는 `mbstr` 로 지정된 버퍼에 저장된 멀티 바이트 문자들로 `wcstr` 로 지정된 와이드 문자 문자열을 변환합니다. 이 때 `mbstate` 에 포함된 변환 상태를 사용합니다.  이러한 조건 중 하나가 충족 될 때까지 변환은 문자마다 계속합니다.  
  
-   와이드 null 문자를 발생합니다.  
  
-   변환할 수 없는 와이드 문자를 발생합니다.  
  
-   `mbstr` 버퍼에 저장되는 바이트의 수는 `count` 와 같습니다.  
  
 대상 문자열은 항상 null로 끝납니다. \(오류의 경우에도\)  
  
 `count`가 특별한 값 [\_TRUNCATE](../../c-runtime-library/truncate.md) 인 경우, null 종료의 여지가 남겨진 동안 대상 버퍼에 맞도록 `wcsrtombs_s` 는 많은 문자열을 변환합니다.  
  
 만일 `wcsrtombs_s` 가 성공적으로 소스 문자열을 변환하는 경우, 이것은 null 종결자를 포함한 변환된 문자열의 바이트들의 크기를 `*``pReturnValue` 로 넣습니다.\( `NULL`가 아닌 `pReturnValue` 를 제공합니다.\)  `mbstr` 인수는 `NULL` 이고 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다.  `mbstr` 가 `NULL` 인 경우, `count` 는 무시 됩니다.  
  
 `wcsrtombs_s` 가 멀티 바이트 문자로 변한 될 수 없는 와이드 문자를 만나면, `*``pReturnValue` 에 \-1을 넣고 대상 버퍼에 빈 문자열을 설정하고 `errno` 를 `EILSEQ` 로 설정하고 `EILSEQ` 를 반환합니다.  
  
 만일 시퀀스에서 `wcstr` 와 `mbstr` 오버랩을 가리키는 경우, `wcsrtombs_s` 의 동작은 정의되지 않습니다.  `wcsrtombs_s` 는 현재 로캘의 LC\_TYPE 범주에 영향을 미칩니다.  
  
> [!IMPORTANT]
>  되도록 `wcstr` 및 `mbstr` 가 겹치지 않도록 하고, `count` 가 변환할 와이드 문자의 수를 올바르게 반영하도록 합니다.  
  
 `wcsrtombs_s` 함수는 이것의 재시작 가능성이라는면에서 [wcstombs\_s, \_wcstombs\_s\_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) 과는 다릅니다.  변환 상태는 이후의 호출을 위해 같거나 다른 다시 시작할 수 있는 함수들로 `mbstate` 에 저장됩니다.  재 시작 가능하거나 그렇지 않은 함수들을 혼용할 때 결과들은 정의되지 않습니다.  예를 들어, `wcstombs_s.` 대신 `wcsrtombs_s` 이 사용되었다면, 응용 프로그램은 `wcslen` 보다 `wcsrlen` 을 사용합니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 예외  
 `wcsrtombs_s` 함수는 실행되는 동안, 현재 스레드가 `setlocale` 를 호출하는 함수가 필요없는 안전한 멀티스레드이고 `mbstate` 는 null입니다.  
  
## 예제  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
  **문자열이 성공적으로 변환되었습니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wcsrtombs_s`|\<wchar.h\>|  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)