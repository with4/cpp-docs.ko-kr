---
title: "strtof, _strtof_l, wcstof, _wcstof_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strtof_l"
  - "wcstof"
  - "strtof"
  - "_wcstof_l"
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
  - "_tcstof"
  - "_tcstof_l"
  - "stdlib/strtof"
  - "strtof"
  - "stdlib/_strtof_l"
  - "_strtof_l"
  - "corecrt_wstdlib/wcstof"
  - "wcstof"
  - "corecrt_wstdlib/_wcstof_l"
  - "_wcstof_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtof_l 함수"
  - "_tcstof 함수"
  - "_tcstof_l 함수"
  - "_wcstof_l 함수"
  - "strtof 함수"
  - "wcstof 함수"
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# strtof, _strtof_l, wcstof, _wcstof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 단정밀도 부동 소수점 값으로 변환합니다.  
  
## 구문  
  
```  
float strtof(  
   const char *nptr,  
   char **endptr   
);  
float _strtof_l(  
   const char *nptr,  
   char **endptr,  
   _locale_t locale  
);  
float wcstof(  
   const wchar_t *nptr,  
   wchar_t **endptr   
);  
float wcstof_l(  
   const wchar_t *nptr,  
   wchar_t **endptr,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `nptr`  
 변환할 Null 종료 문자열입니다.  
  
 `endptr`  
 검색을 중지하는 문자에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `strtof`는 오버플로가 발생되는 시기를 제외하고 함수가 \+ \/\-`HUGE_VALF`를 반환하는 경우에 부동 소수점 숫자의 값을 반환합니다.  `HUGE_VALF`의 기호는 나타낼 수 없는 값의 기호에 해당합니다.  `strtof`는 변환을 수행할 수 없거나 언더플로가 발생하는 경우 0을 반환합니다.  
  
 `wcstof`이 analogously 값을 `strtof`에 반환 합니다.  두 가지의 함수에 대해서 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 오버플로 또는 언더플로가 발생하여 잘못된 매개 변수 처리기를 호출하는 경우 `errno`를 `ERANGE`로 설정합니다.  
  
 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.  
  
## 설명  
 각 함수는 입력 문자열 `nptr`을 `float`으로 변환합니다.  `strtof` 함수는 `nptr`을 단정밀도 값으로 변환합니다.  `strtof`는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 문자열 `nptr` 읽기를 중단합니다.  이는 null 종결 문자일 수 있습니다.  `wcstof`는 `strtof`의 와이드 문자 버전이며, `nptr` 인수는 와이드 문자 문자열입니다.  그렇지 않으면 이러한 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcstof`|`strtof`|`strtof`|`wcstof`|  
|`_tcstof_l`|`_strtof_l`|`_strtof_l`|`_wcstof_l`|  
  
 현재 로캘의 `LC_NUMERIC` 범주 설정은 `nptr`에서 기수 문자 인식 여부를 결정합니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 함수는 현재 로캘을 사용합니다. 접미사가 있는 함수는 대신 전달된 로캘을 사용한다는 점을 제외하면 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `endptr`이 `NULL`이 아닌 경우 검색을 중지시키는 문자에 대한 포인터는 `endptr`가 가리키는 위치에 저장됩니다.  변환을 수행할 수 없는 경우\(유효 숫자를 찾을 수 없거나 잘못된 기준이 지정됨\) `nptr`의 값은 `endptr`가 가리키는 위치에 저장됩니다.  
  
 `strtof`에서는 다음 양식의 문자열을 가리키는 `nptr`를 예상합니다.  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E`}\[`sign`\]`digits`\]  
  
 `whitespace`는 무시되는 공백이나 탭 문자로 구성될 수 있으며 `sign`은 더하기\(`+`\) 또는 빼기\(`–`\)이며 `digits`는 하나 이상의 숫자입니다.  기수 문자 앞에 자릿수가 나타나지 않는 경우 하나 이상의 자릿수가 기수 문자 뒤에 나타나야 합니다.  10 진수는 소개서를 구성하는 지수\(`d`, `D`, `e`, 또는 `E`\)와 선택적으로 서명된 정수 다음에 올 수 있습니다.  지수부 또는 기수 문자가 나타나지 않는 경우 기수 문자는 문자열의 마지막 숫자를 따릅니다.  이 폼에 맞지 않는 첫 번째 문자는 검색을 중지합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strtof`, `_strtof_l`|\<stdlib.h\>|  
|`wcstof`, `_wcstof_l`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strtof.c  
// This program uses strtof to convert a  
// string to a single-precision value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char *string;  
   char *stopstring;  
   float x;  
  
   string = "3.14159This stopped it";  
   x = strtof(string, &stopstring);  
   printf("string = %s\n", string);  
   printf("   strtof = %f\n", x);  
   printf("   Stopped scan at: %s\n\n", stopstring);  
}  
```  
  
  **문자열 \= 3.14159This stopped it**  
 **strtof \= 3.141590**  
 **검색이 중지된 위치: 중지한 항목**   
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)   
 [strtod, \_strtod\_l, wcstod, \_wcstod\_l](../../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)   
 [strtol, wcstol, \_strtol\_l, \_wcstol\_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
 [strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)