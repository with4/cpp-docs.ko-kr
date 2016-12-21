---
title: "_mbsnbset, _mbsnbset_l | Microsoft Docs"
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
  - "_mbsnbset"
  - "_mbsnbset_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbset"
  - "mbsnbset_l"
  - "_mbsnbset"
  - "_mbsnbset_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbset 함수"
  - "_mbsnbset_l 함수"
  - "_tcsnset 함수"
  - "_tcsnset_l 함수"
  - "mbsnbset 함수"
  - "mbsnbset_l 함수"
  - "tcsnset 함수"
  - "tcsnset_l 함수"
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbset, _mbsnbset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

처음은 `n` 지정된 문자를 멀티 바이트 문자 문자열의 바이트를 설정하세요.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_mbsnbset\_s, \_mbsnbset\_s\_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned char *_mbsnbset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnbset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 변경할 문자열입니다.  
  
 `c`  
 싱글바이트 문자와 멀티 바이트 문자 설정합니다.  
  
 `count`  
 설정해야하는 바이트 수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbsnbset` 변경된 문자열에 대한 포인터를 반환합니다.  
  
## 설명  
 이 `_mbsnbset` 와 `_mbsnbset_l` 함수는 `c` 에서 `str` 의 첫 `count` 바이트를 설정합니다.   `count`  이  `str` 의 길이보다 큰 경우,  `count` 대신에   `str`  이 사용됩니다.   만약 `c` 이 멀티 바이트 문자 및 마지막으로 `count`으로 지정 된 바이트를 전적으로 설정할 수 없는 경우, 마지막 바이트 공백 문자로 채워집니다.  `_mbsnbset` 와 `_mbsnbset_l`은 `str`의 끝에 null 을 종료로 두지 않습니다.  
  
 `_mbsnbset` 와 `_mbsnbset_l`은, `c` 보다 `count` 문자가 `count` 바이트들로 설정하는 것을 제외한, `_mbsnset`와 유사합니다.  
  
 만약 `str` 이 `NULL` 혹은 `count` 이 0인 경우, 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명된 잘못된 매개변수 예외를 생성합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  또한, `c` 이 유효한 멀티 바이트 문자가 아닌 경우, `errno` 은 `EINVAL` 으로 설정하고 공백은 대신 사용됩니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  이 함수가 사용하는 로캘 종속 동작을 위한 현재 로캘의 `_mbsnbset` 버전; `_mbsnbset_l` 버전은 대신에 통과한 로캘 매기 변수를 사용하는 동일한 예외입니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 **보안 정보** 이 API 버퍼 오버런 문제에 대한 상태로 잠재적인 위협을 초래합니다.  버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnbset`|\<mbstring.h\>|  
|`_mbsnbset_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_mbsnbset.c  
// compile with: /W3  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset( string, '*', 4 ); // C4996  
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
## Output  
  
```  
Before: This is a test  
After:  **** is a test  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)