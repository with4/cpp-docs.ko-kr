---
title: "mbstowcs, _mbstowcs_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbstowcs"
  - "_mbstowcs_l"
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
  - "mbstowcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbstowcs_l 함수"
  - "mbstowcs 함수"
  - "mbstowcs_l 함수"
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# mbstowcs, _mbstowcs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티 바이트 문자의 시퀀스를 해당하는 와이드 문자의 시퀀스로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [mbstowcs\_s, \_mbstowcs\_s\_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
size_t mbstowcs(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count   
);  
size_t _mbstowcs_l(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t mbstowcs(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _mbstowcs_l(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `wcstr`  
 주소는 와이드 문자의 시퀀스입니다.  
  
 \[in\] `mbstr`  
 종료된 멀티 바이트 문자 null 의 시퀀스의 주소입니다.  
  
 \[in\] `count`  
 변환을 위한 멀티바이트 문자들의 최대 문자 수입니다.  
  
 \[in\] `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 만일 성공적으로 `mbstowcs` 이 원본문자열을 변환한 경우, 변환된 멀티바이트 문자의 수를 반환합니다.  만일 `wcstr` 매개변수가 `NULL` 인 경우, 이 함수는 목적지 문자열의\(와이드 문자에서\) 필요한 크기를 반환합니다.  만일 `mbstowcs` 가 잘못된 멀티바이트 문자를 발견한 경우, \-1을 반환합니다.  반환값이 `count` 이라면, 와이드 문자 문자열은 null로 끝나지 않습니다.  
  
> [!IMPORTANT]
>  되도록 `wcstr` 및 `mbstr` 가 겹치지 않도록 하고, `count` 가 변환할 멀티바이트 문자의 수를 올바르게 반영하도록 합니다.  
  
## 설명  
 `mbstowcs` 함수는 현재 로캘에서 결정된 와이드 문자들의 문자열을 위해 `mbstr` 로 지정된 멀티바이트 문자들을 `count` 의 최대 숫자로 변환합니다.  이것은 `wcstr`*.* 로 표현된 주소에 결과 와이드 문자 문자열을 저장합니다. 결과는 `mbtowc` 의 일련의 호출과 유사합니다.  `mbstowcs` 가 `count` 이 발생하기 전이나 발생할 때 단일 바이트 nulll 문자\('\\0'\)를 발견한 경우, null문자를 와이드 문자 null 문자\(L'\\0'\)로 변환하고 멈춥니다.  따라서, 와이드 문자 문자열은 `wcstr` 에서 null로 끝납니다. 이는 오직 null 문자를 변환하는 동안 이루어집니다.  만일 `wcstr` 와 `mbstr` 에 의해 지정된 시퀀스가 겹쳐질 경우, 동작은 정의되지 않습니다.  
  
 만일 `wcstr` 인수가 `NULL` 인 경우, `mbstowcs` 는 null 종결자를 포함하지 않는 변환된 와이드 문자들의 수를 반환합니다.  소스 문자열은 올바른 값을 반환하기 위해 null로 종료되어야합니다.  null로 종결 되는 결과 와이드 문자열이 필요한 경우, 반환 되는 값에 추가합니다.  
  
 만일 `mbstr` 인수가 `NULL` 이거나 `count` 가 \>`INT_MAX` 인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서 설명된 것처럼 잘못된 매개변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, errno는 `EINVAL` 로 설정되고 이 함수는 \-1을 반환합니다.  
  
 `mbstowcs` 는 로캘 종속 동작에 대해 현재 로캘을 사용합니다; `_mbstowcs_l`  는 전달된 로캘을 대신 사용하는 것을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`mbstowcs`|\<stdlib.h\>|  
|`_mbstowcs_l`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_mbstowcs.c  
// compile with: /W3  
// illustrates the behavior of the mbstowcs function  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main( void )  
{  
    size_t size;  
    int nChar = 2; // number of characters to convert  
    int requiredSize;  
  
    unsigned char    *pmbnull  = NULL;  
    unsigned char    *pmbhello = NULL;  
    char* localeInfo;  
  
    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters  
    wchar_t *pwc;  
  
    /* Enable the Japanese locale and codepage */  
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");  
    printf("Locale information set to %s\n", localeInfo);  
  
    printf( "Convert to multibyte string:\n" );  
  
    requiredSize = wcstombs( NULL, pwchello, 0); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    printf("  Required Size: %d\n", requiredSize);  
  
    /* Add one to leave room for the null terminator. */  
    pmbhello = (unsigned char *)malloc( requiredSize + 1);  
    if (! pmbhello)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    if (size == (size_t) (-1))  
    {  
        printf("Couldn't convert string. Code page 932 may"  
                " not be available.\n");  
        return 1;  
    }  
    printf( "  Number of bytes written to multibyte string: %u\n",  
            (unsigned int) size );  
    printf( "  Hex values of the " );  
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",  
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );  
    printf( "  Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");  
  
    printf( "Convert back to wide-character string:\n" );  
  
    /* Assume we don't know the length of the multibyte string.  
     Get the required size in characters, and allocate enough space. */  
  
    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996  
    /* Add one to leave room for the NULL terminator */  
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));  
    if (! pwc)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996  
    if (size == (size_t) (-1))  
    {  
       printf("Couldn't convert string--invalid multibyte character.\n");  
    }  
    printf( "  Characters converted: %u\n", (unsigned int)size );  
    printf( "  Hex value of first 2" );  
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );  
    free(pwc);  
    free(pmbhello);  
}  
```  
  
  **Japanese\_Japan.932로 설정된 로캘 정보**  
**멀티 바이트 문자열로 변환합니다.**  
 **필요한 크기: 4**  
 **멀티 바이트 문자열로 쓸 바이트 수: 4**  
 **멀티 바이트 문자의 16진수 값: 0x82 0xa0 0x82 0xa1**  
 **코드 페이지 932는 선행바이트로 0x81에서 0x9f를 사용합니다.**  
**와이드 문자열로 변환합니다:**  
 **변환된 문자: 2**  
 **최초 2 와이드 문자의 16진수 값: 0x3042 0x3043**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)