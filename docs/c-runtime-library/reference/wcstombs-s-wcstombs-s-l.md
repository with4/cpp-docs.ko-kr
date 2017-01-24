---
title: "wcstombs_s, _wcstombs_s_l | Microsoft Docs"
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
  - "_wcstombs_s_l"
  - "wcstombs_s"
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
  - "wcstombs_s"
  - "_wcstombs_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcstombs_s 함수"
  - "문자열 변환, 와이드 문자"
  - "변환 하는 와이드 문자"
  - "_wcstombs_s_l 함수"
  - "wcstombs_s_l 함수"
  - "문자를 변환"
  - "문자열 변환, 멀티 바이트 문자열"
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcstombs_s, _wcstombs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. 버전의 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) 에 설명 된 대로 보안이 강화 된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)합니다.  
  
## 구문  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `pReturnValue`  
 변환된 문자 수입니다.  
  
 \[out\] `mbstr`  
 결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.  
  
 \[in\]`sizeInBytes`  
 `mbstr` 버퍼의 크기\(바이트\)입니다.  
  
 \[in\] `wcstr`  
 변환할 와이드 문자열을 가리킵니다.  
  
 \[in\] `count`  
 에 저장 하는 바이트의 최대 수는 `mbstr` 버퍼에 null 종결 문자를 포함 하지 않고 또는 [\_TRUNCATE](../../c-runtime-library/truncate.md)합니다.  
  
 \[in\] `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공 시 0, 실패 하면 오류 코드가 있습니다.  
  
|오류 조건|반환 값 및 `errno`|  
|-----------|--------------------|  
|`mbstr`은 `NULL` 및 `sizeInBytes` \> 0입니다.|`EINVAL`|  
|`wcstr`가 `NULL`인 경우|`EINVAL`|  
|대상 버퍼가 너무 작아 변환 문자열을 포함할 수 없습니다\(`count`가 `_TRUNCATE`가 아닌 경우 아래 설명 참조\).|`ERANGE`|  
  
 이러한 조건 중 하나라도 발생 하는 경우는 잘못 된 매개 변수는 호출 예외에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 계속해서 실행하도록 허용된 경우 이 함수는 오류 코드를 반환하고 `errno`를 표에 표시된 대로 설정합니다.  
  
## 설명  
 `wcstombs_s` 함수는 `wcstr`가 가리키는 와이드 문자를 `mbstr`가 가리키는 멀티바이트 문자로 변환합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.  
  
-   null 와이드 문자가 있는 경우  
  
-   변환할 수 없는 와이드 문자가 있는 경우  
  
-   `mbstr` 버퍼에 저장된 바이트 수가 `count`와 같은 경우  
  
 대상 문자열은 항상 null로 끝납니다\(오류 발생 시도 포함\).  
  
 경우 `count` 특수 값 [\_TRUNCATE](../../c-runtime-library/truncate.md), 다음 `wcstombs_s` 변환 만큼 수 있는 만큼 문자열의 null 종결자에 대 한 공간은 남겨 두고 대상 버퍼에 적합 합니다.  
  
 `wcstombs_s`가 소스 문자열을 성공적으로 변환하는 경우 null 종결자를 포함하여 변환된 문자열의 크기\(바이트\)를 `*``pReturnValue`에 배치합니다\(제공된 `pReturnValue`가 `NULL`이 아닌 경우\).`mbstr` 인수가 `NULL`이며 필요한 버퍼 크기를 결정하는 방법을 제공하는 경우에도 발생합니다.`mbstr`이 `NULL`인 경우 `count`가 무시됩니다.  
  
 `wcstombs_s`가 멀티바이트 문자로 변환될 수 없는 와이드 문자를 만나면 `*``pReturnValue`에 0을 넣고, 대상 버퍼를 빈 문자열로 설정하고, `errno`를 `EILSEQ`로 설정하고, `EILSEQ`를 반환합니다.  
  
 `wcstr`이 가리키는 시퀀스와 `mbstr`이 가리키는 시퀀스가 겹치는 경우 `wcstombs_s`의 동작이 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `wcstr`와 `mbstr`이 겹치지 않고 `count`가 변환할 와이드 문자 수를 정확하게 반영하도록 합니다.  
  
 `wcstombs_s`는 로캘 종속 동작에 대해 현재 로캘을 사용합니다. `_wcstombs_s_l`은 대신 전달된 로캘을 사용하는 것을 제외하고는 `wcstombs`와 같습니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wcstombs_s`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 프로그램은 `wcstombs_s` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
와이드 문자 문자열 변환: 문자 변환: 14 멀티 바이트 문자: Hello, world.  
```  
  
## 해당 .NET Framework 항목  
 적용할 수 없음 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)