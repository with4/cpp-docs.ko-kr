---
title: "_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_atoldbl"
  - "_atoldbl_l"
  - "_atodbl"
  - "_atoflt"
  - "_atoflt_l"
  - "_atodbl_l"
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
  - "_atoflt"
  - "_atoflt_l"
  - "atodbl_l"
  - "atoflt_l"
  - "_atoldbl"
  - "_atoldbl_l"
  - "atodbl"
  - "_atodbl_l"
  - "atoldbl"
  - "atoflt"
  - "atoldbl_l"
  - "_atodbl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_atodbl 함수"
  - "_atoldbl_l 함수"
  - "atoflt 함수"
  - "atoflt_l 함수"
  - "atoldbl 함수"
  - "_atoldbl 함수"
  - "atodbl_l 함수"
  - "_atoflt_l 함수"
  - "atoldbl_l 함수"
  - "atodbl 함수"
  - "문자열 변환, 부동 소수점 값으로"
  - "_atoflt 함수"
  - "_atodbl_l 함수"
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 double \(`_atodbl`\), long double \(`_atoldbl`\), 또는 float \(`_atoflt`\) 으로 변환합니다.  
  
## 구문  
  
```  
int _atodbl(  
   _CRT_DOUBLE * value,  
   char * str  
);  
int _atodbl_l (  
   _CRT_DOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoldbl(  
   _LDOUBLE * value,  
   char * str  
);  
int _atoldbl_l (  
   _LDOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoflt(  
   _CRT_FLOAT * value,  
   const char * str  
);  
int _atoflt_l(  
   _CRT_FLOAT * value,  
   const char * str,  
   locale_t locale  
);  
```  
  
#### 매개 변수  
 `value`  
 문자열을 부동 소수점 값으로 변환하여 생성된 double, long double, 또는 float 값입니다.  이러한 값은 구조체에 래핑됩니다.  
  
 `str`  
 부동 소수점 값으로 변환하기 위해 분석 되는 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공하면 0를 반환합니다.  가능한 오류 코드는 `_UNDERFLOW` 또는 `_OVERFLOW`이며, Math.h 에 정의 되어있습니다.  
  
## 설명  
 이러한 함수는 문자열을 부동 소수점 값으로 변환합니다.  이러한 함수와 `atof` 함수 패밀리의 차이점은 이러한 함수는 부동 소수점 코드를 생성하지 않으며 하드웨어 예외를 발생시키지 않는 다는 것입니다.  대신에 오류 조건은 오류 코드로 보고 됩니다.  
  
 만약 문자열이 부동 소수점 값으로서 유효한 해석을 가지지 않는다면 `value` 는 0으로 설정 되고 반환 값은 0이 됩니다.  
  
 현재 스레드 로캘 대신에 전달 된 로캘 매개 변수를 사용하는 경우를 제외하고는 `_l` 접미사가 있는 이러한 함수의 버전과 접미사가 없는 버전은 동일합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_atodbl`, `_atoldbl`, `_atoflt`<br /><br /> `_atodbl_l`, `_atoldbl_l`, `_atoflt_l`|\<stdlib.h\>|  
  
## 예제  
  
```  
// crt_atodbl.c  
// Uses _atodbl to convert a string to a double precision  
// floating point value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
   char str1[256] = "3.141592654";  
   char abc[256] = "abc";  
   char oflow[256] = "1.0E+5000";  
   _CRT_DOUBLE dblval;  
   _CRT_FLOAT fltval;  
   int retval;  
  
   retval = _atodbl(&dblval, str1);  
  
   printf("Double value: %lf\n", dblval.x);  
   printf("Return value: %d\n\n", retval);  
  
   retval = _atoflt(&fltval, str1);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // A non-floating point value: returns 0.  
   retval = _atoflt(&fltval, abc);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // Overflow.  
   retval = _atoflt(&fltval, oflow);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   return 0;  
}  
```  
  
  **Double value: 3.141593**  
**Return value: 0**  
**Float value: 3.141593**  
**Return value: 0**  
**Float value: 0.000000**  
**Return value: 0**  
**Float value: 1.\#INF00**  
**Return value: 3**   
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)