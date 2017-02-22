---
title: "atof, _atof_l, _wtof, _wtof_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtof_l"
  - "atof"
  - "_atof_l"
  - "_wtof"
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
  - "_tstof"
  - "_ttof"
  - "atof"
  - "stdlib/atof"
  - "math/atof"
  - "_atof_l"
  - "stdlib/_atof_l"
  - "math/_atof_l"
  - "_wtof"
  - "corecrt_wstdlib/_wtof"
  - "_wtof_l"
  - "corecrt_wstdlib/_wtof_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tstof 함수"
  - "atof_l 함수"
  - "_atof_l 함수"
  - "atof 함수"
  - "_tstof 함수"
  - "_ttof 함수"
  - "wtof 함수"
  - "_wtof_l 함수"
  - "ttof 함수"
  - "wtof_l 함수"
  - "_wtof 함수"
  - "문자열 변환, 부동 소수점 값으로"
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# atof, _atof_l, _wtof, _wtof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 double로 변환합니다.  
  
## 구문  
  
```  
double atof(  
   const char *str   
);  
double _atof_l(  
   const char *str,  
   _locale_t locale  
);  
double _wtof(  
   const wchar_t *str   
);  
double _wtof_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 변환할 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 각 함수는 입력 문자를 숫자로 해석하여 생성된 `double` 값을 반환합니다.  만약 입력값이 해당 형식의 값으로 변환될 수 없을 경우 반환 값은 0입니다.  
  
 범위를 벗어난 모든 경우 errno는 `ERANGE`로 설정됩니다.  전달된 매개 변수가 `NULL`이 되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명과 같이 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL`로 설정하고 0을 반환합니다.  
  
## 설명  
 이러한 함수들은 문자열을 배정밀도, 부동 소수점 값으로 변환합니다.  
  
 입력 문자열은 지정한 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다.  함수는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중단합니다.  이 문자는 문자열을 종결하는 null 문자\('\\0' 또는 L'\\0'\)일 수 있습니다.  
  
 `str` 인수는 `atof` 와 `_wtof` 에 다음과 같은 형식을 가집니다.  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E` }\[`sign`\]`digits`\]  
  
 `whitespace`는 무시되는 공백이나 탭 문자로 구성됩니다 `sign`은 더하기\(\+\) 또는 빼기\(–\)이며 `digits`는 하나 이상의 10진 숫자입니다.  만약 소수점 앞에 숫자가 표시되지 않는 경우 적어도 하나는 소수점 뒤에 표시되어야 합니다.  10 진수 숫자는 지수뒤에 오고 처음 문자는\(`d`, `D`, `e`, 또는 `E`\)로 구성되며 선택적으로 10진 정수로 표현됩니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tstof`|`atof`|`atof`|`_wtof`|  
|`_ttof`|`atof`|`atof`|`_wtof`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`atof`|\<stdlib.h\> 또는 \<math.h\>|  
|`_atof_l`|\<stdlib.h\> 또는 \<math.h\>|  
|`_wtof`, `_wtof_l`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
## 예제  
 이 프로그램은 `atof` 함수를 사용하여 문자로 저장된 수가 숫자 값으로 변환되는 것을 보여 줍니다.  
  
```  
// crt_atof.c  
//  
// This program shows how numbers stored as   
// strings can be converted to numeric  
// values using the atof function.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    double  value = 0;  
  
    // An example of the atof function  
    // using leading and training spaces.  
    str = "  3336402735171707160320 ";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // Another example of the atof function  
    // using the 'd' exponential formatting keyword.  
    str = "3.1412764583d210";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // An example of the atof function  
    // using the 'e' exponential formatting keyword.  
    str = "  -2309.12E-15";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
}  
```  
  
  **기능: atof \("3336402735171707160320"\) \= 3.336403e \+ 021**  
**기능: atof \("3.1412764583d210"\) \= 3.141276e \+ 210**  
**기능: atof \("\-2309.12E\-15"\) \=\-2.309120e\-012**   
## 해당 .NET Framework 항목  
  
-   [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
-   [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)