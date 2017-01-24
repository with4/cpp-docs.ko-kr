---
title: "wcstombs, _wcstombs_l | Microsoft Docs"
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
  - "wcstombs"
  - "_wcstombs_l"
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
  - "wcstombs"
  - "_wcstombs_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wcstombs_l 함수"
  - "문자, 변환"
  - "문자열 변환, 멀티바이트 문자열"
  - "문자열 변환, 와이드 문자"
  - "wcstombs 함수"
  - "wcstombs_l 함수"
  - "와이드 문자, 변환"
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wcstombs, _wcstombs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자의 시퀀스를 해당하는 멀티 바이트 문자의 시퀀스로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [wcstombs\_s, \_wcstombs\_s\_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### 매개 변수  
 `mbstr`  
 주소는 멀티바이트 문자의 시퀀스입니다.  
  
 `wcstr`  
 주소는 와이드 문자의 시퀀스입니다.  
  
 `count`  
 멀티바이트 출력 문자열에서 저장할 수 있는 최대 바이트의 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 만약 `wcstombs`가 성공적으로 멀티바이트 문자열을 변환했다면, 그것은 종료 `NULL`\(만약 있다면\)를 제외하고 멀티바이트 출력 문자열에 쓰여진 바이트의 숫자를 반환합니다.  `mbstr` 인수가 `NULL`이면, `wcstombs`은 대상 문자열의 요구 크기를 바이트의 형태로 반환합니다.  만약 `wcstombs`가 와이드 문자와 부딪혔을 경우, 그것은 멀티 바이트 문자로 변환될 수 없고, \-1 캐스트를 형식 `size_t`로 반환하고 `errno`을 `EILSEQ`로 설정합니다.  
  
## 설명  
 `wcstombs` 함수는 `wcstr`가 가리키는 와이드 문자의 문자열을 해당하는 멀티 바이트 문자로 변환하고 그 결과를 `mbstr` 배열에 저장합니다.  `count` 매개 변수는 멀티 바이트 출력 문자열에 저장할 수 있는 바이트의 최대 숫자를 표시합니다. \(이는 `mbstr`의 크기입니다.\)  일반적으로, 와이드 문자열을 변환할 때 필요한 바이트의 수는 알려져 있지 않습니다.  일부 와이드 문자는 출력 문자열에서 오직 1바이트만 요구할 것입니다. 그 외에는 2바이트를 요구합니다.  모든 와이드 문자\(`NULL` 와이드 문자를 포함하여\) 멀티 바이트 출력 문자열에 두 바이트가 있는 경우, 결과는 맞는 것이 보장됩니다.  
  
 `wcstombs` 이 `count` 가 발생할 때나 그 이 전에 와이드 null문자\(L'\\0'\)를 발견한다면, 이것은 8비트 0으로 변환하고 멈춥니다.  따라서 멀티 바이트 문자 문자열에서 `mbstr`는 null로 끝나는 경우에 `wcstombs` 와이드 null 문자로 변환 하는 동안 발생 합니다.  만일 `wcstr` 와 `mbstr` 에 의해 가르켜진 시퀀스가 겹쳐질 경우, `wcstombs` 의 동작은 정의되지 않습니다.  
  
 `mbstr` 인수가 `NULL`이면, `wcstombs`은 대상 문자열의 요구 크기를 바이트의 형태로 반환합니다.  
  
 `wcstombs` 매개 변수의 유효성을 검사합니다.  만약 `wcstr`가 `NULL`이거나 `count`가 `INT_MAX`보다 더 큰 경우, 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다.  계속 실행하는 것이 허용되었다면, 함수는 `errno`을 `EINVAL`로 설정하고 \-1을 반환합니다.  
  
 `wcstombs` 는 로캘 종속 동작에 대해 현재 로캘을 사용 합니다. `_wcstombs_l` 는 대신에 전달 된 로캘을 사용 하는 것을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 C\+\+에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wcstombs`|\<stdlib.h\>|  
|`_wcstombs_l`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 프로그램은 `wcstombs` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
  **와이드 문자열을 변환합니다.**  
 **변환된 문자: 13**  
 **멀티 바이트 문자: Hello, world.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)