---
title: "ecvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ecvt"
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
  - "ecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ecvt 함수"
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _ecvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열로 `double` 을 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### 매개 변수  
 `value`  
 변환될 수 있는 숫자  
  
 `count`  
 저장된 자릿수입니다.  
  
 `dec`  
 소수점 위치를 저장합니다.  
  
 `sign`  
 변환된 숫자의 부호입니다.  
  
## 반환 값  
 `_ecvt` 는 숫자의 문자열에 대한 포인터를 반환합니다; 만일 오류가 발생하면 NULL을 반환합니다.  
  
## 설명  
 `_ecvt` 함수는 부동 소수점 숫자를 문자열로 변환합니다.  `value` 매개 변수는 변환된 부동 소수점 숫자입니다.  이 함수는 문자열로 `value` 의 숫자를 최대 `count` 로 저장하고 null 문자 \('\\0\)을 추가합니다.  만일 `value` 에서 자리수가 `count` 를 넘는 경우, 반올림 됩니다.  `count` 보다 적은 자릿수인 경우, 문자열은 0으로 채워집니다.  
  
 `_ecvt` 로 반환 되는 전체 자릿수는 `_CVTBUFSIZE`를 넘어서는 안됩니다.  
  
 숫자만이 문자열에 저장됩니다.  소수점의 위치 및 `value`의 부호는 호출 이후 `dec`과 `sign`로부터 얻을 수 있습니다.  `dec` 매개 변수는 문자열의 시작 부분에 대한 소수점의 위치를 제공하는 정수의 값을 가리킵니다.  0 또는 음수 값은 소수점이 첫째 자리의 왼쪽에 위치하는 것을 가리킵니다.  `sign` 매개 변수는 변환 된 숫자의 부호를 나타내는 정수를 가리킵니다.  정수의 값이 0이면, 양수입니다.  그렇지 않으면 음수입니다.  
  
 `_ecvt` 및 `_fcvt`에서 `count` 매개 변수의 번역 차이입니다.  `_ecvt`는 `count`을 출력 문자열의 전체 자릿수로 해석하며, `_fcvt`은 `count`를 소수점 뒤의 자릿수로 해석합니다.  
  
 `_ecvt`와 `_fcvt` 는 변환에 정적으로 할당된 버퍼를 사용합니다.  이러한 루틴 중 하나를 호출 할 때마다 이전 호출의 결과를 삭제합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  만일 `dec` 또는 `sign` 이 NULL이거나 `count` 이 0이라면, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `errno` 는 `EINVAL` 와 NULL을 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_ecvt`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
  **소스: 3.1415926535 버퍼: '3141592654' 10진수: 1 부호: 0**   
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)