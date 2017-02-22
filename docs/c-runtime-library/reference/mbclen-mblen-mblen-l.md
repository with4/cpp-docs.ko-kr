---
title: "_mbclen, mblen, _mblen_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbclen"
  - "mblen"
  - "_mblen_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mblen"
  - "ftclen"
  - "_mbclen"
  - "tclen"
  - "_ftclen"
  - "_tclen"
  - "mbclen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbclen 함수"
  - "_mblen_l 함수"
  - "_tclen 함수"
  - "mbclen 함수"
  - "mblen 함수"
  - "mblen_l 함수"
  - "tclen 함수"
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _mbclen, mblen, _mblen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

멀티 바이트 문자의 유효성을 확인하고 길이 가져옵니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
size_t _mbclen(  
   const unsigned char *c   
);  
int mblen(  
   const char *mbstr,  
   size_t count   
);  
int _mblen_l(  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 멀티바이트 문자.  
  
 `mbstr`  
 멀티 바이트 문자 바이트 시퀀스의 주소입니다.  
  
 `count`  
 확인하는 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbclen` 는 멀티 바이트 문자 `c` 가 1 혹은 2 바이트 인지에 따라 1 혹은 2를 반환합니다.  이 `_mbclen` 을 위한 반환되는 오류가 없습니다.  만약 `mbstr` 가 `NULL` 이 아닌 경우, `mblen` 는 멀티 바이트 문자의 바이트에 대한 길이를 반환합니다.  만약 `mbstr` 이 `NULL` 혹은 와이드 문자 null 문자를 가리키는 경우, `mblen` 는 0을 반환합니다.  이 `mbstr` 를 가리키는 개체가 첫 `count` 문자 내부에 유효한 멀티 바이트 문자인 양식이 아닌 경우, `mblen` 는 \-1을 반환합니다.  
  
## 설명  
 이 `_mbclen` 함수는 멀티 바이트 문자 `c` 인 바이트 길이를 반환합니다.  이 `c` 는 `_mbclen` 이 예측할 수 없는 결과인 `_ismbblead` 암시적 호출로 부터 결정되지 않아서 멀티 바이트의 문자의 선행 바이트를 가리키지 않습니다.  
  
 `mblen` 는 유효한 멀티 바이트 문자이고 유효한 코드 페이지에 연관된 멀티 바이트 문자가 결정하는 경우 `mbstr` 의 바이트 길이를 반환합니다.  `mblen` 는 `count` 혹은 `mbstr`이 포함된 적은 바이트 를 조사하나, `MB_CUR_MAX` 바이트보다 더 많은 것은 아닙니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tclen`|매크로 또는 인라인 함수에 매핑|`_mbclen`|매크로 또는 인라인 함수에 매핑|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbclen`|\<mbstring.h\>|  
|`mblen`|\<stdlib.h\>|  
|`_mblen_l`|\<stdlib.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_mblen.c  
/* illustrates the behavior of the mblen function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc = (char *)malloc( sizeof( char ) );  
    wchar_t  wc   = L'a';  
  
    printf( "Convert wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );  
  
    pmbc = NULL;  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );  
}  
```  
  
## Output  
  
```  
Convert wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Length in bytes of multibyte character 61: 1  
Length in bytes of NULL multibyte character 0: 0  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbccpy, \_mbccpy\_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)   
 [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)