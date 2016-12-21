---
title: "_gcvt | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt"
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
  - "_gcvt"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt 함수"
  - "변환, 부동 소수점을 문자열로"
  - "CVTBUFSIZE"
  - "부동 소수점 함수, 숫자를 문자열로 변환"
  - "gcvt 함수"
  - "숫자, 문자열로 변환"
  - "문자열[C++], 부동 소수점에서 변환"
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _gcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 값을 버퍼에 저장되는 문자열로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)를 참조하십시오.  
  
## 구문  
  
```  
char *_gcvt(   
   double value,  
   int digits,  
   char *buffer   
);  
```  
  
#### 매개 변수  
 `value`  
 변환될 값입니다.  
  
 `digits`  
 저장된 유효 자릿수입니다.  
  
 `buffer`  
 결과에 대한 저장소 위치입니다.  
  
## 반환 값  
 `_gcvt`는 문자열의 자릿수에 대한 포인터를 반환합니다.  
  
## 설명  
 `_gcvt` 함수는 부동 소수점 `value` 을 문자열로 변환하고 \(10진수 및 부호 가능한 바이트 포함\) `buffer` 에 문자열을 저장합니다.  `buffer`는 변환된 값과 자동으로 추가되는 종료 null 문자를 수용하기에 충분히 커야 합니다.  `digits`의 버퍼 크기 \+ 1이 사용되면, 함수는 버퍼의 끝을 덮어씁니다.  변환된 문자열은 소수점을 포함하며 부호와 지수 정보를 포함할 수 있기 때문입니다.  오버플로우에 대한 규정이 없습니다.  `_gcvt`는 10 진수 형식으로 `digits`를 생성하려고 시도합니다.  할수 없는 경우, 지수 형식의 `digits` 숫자를 생성합니다.  따라오는 0들은 변환에서 무시될 수 있습니다.  
  
 `_CVTBUFSIZE` 길이의 `buffer`는 모든 부동 소수점 값에 대해 충분합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  `buffer`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `NULL`을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_gcvt`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_gcvt.c  
// compile with: /W3  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   char buffer[_CVTBUFSIZE];  
   double value = -1234567890.123;  
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );  
   _gcvt( value, 12, buffer ); // C4996  
   // Note: _gcvt is deprecated; consider using _gcvt_s instead  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
  
   printf( "\n" );  
   value = -12.34567890123;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
}  
```  
  
  **The following numbers were converted by \_gcvt\(value,12,buffer\):**  
**buffer: '\-1234567890.12' \(14 chars\)**  
**buffer: '\-1234567890.12' \(14 chars\)**  
**buffer: '\-123456789012' \(13 chars\)**  
**buffer: '\-1.23456789012e\+012' \(19 chars\)**  
**buffer: '\-1234567890.12' \(14 chars\)**  
**buffer: '\-1234567890.12' \(14 chars\)**  
**buffer: '\-0.123456789012' \(15 chars\)**  
**buffer: '\-1.23456789012e\-002' \(19 chars\)**   
## 해당 .NET Framework 항목  
 [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)