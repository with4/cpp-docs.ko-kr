---
title: "_atoi64, _atoi64_l, _wtoi64, _wtoi64_l | Microsoft Docs"
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
  - "_atoi64_l"
  - "_wtoi64"
  - "_atoi64"
  - "_wtoi64_l"
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
  - "_atoi64"
  - "_tstoi64"
  - "_ttoi64"
  - "wtoi64"
  - "_tstoi64_l"
  - "atoi64"
  - "_wtoi64_l"
  - "_wtoi64"
  - "wtoi64_l"
  - "_atoi64_l"
  - "atoi64_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstoi64 함수"
  - "wtoi64 함수"
  - "atoi64_l 함수"
  - "_ttoi64 함수"
  - "문자열 변환, 정수로"
  - "wtoi64_l 함수"
  - "atoi64 함수"
  - "_tstoi64 함수"
  - "_atoi64_l 함수"
  - "_wtoi64_l 함수"
  - "ttoi64 함수"
  - "_wtoi64 함수"
  - "_atoi64 함수"
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _atoi64, _atoi64_l, _wtoi64, _wtoi64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열을 64비트 부호 있는 정수로 변환합니다.  
  
## 구문  
  
```  
__int64 _atoi64(  
   const char *str   
);  
__int64 _wtoi64(  
   const wchar_t *str   
);  
__int64 _atoi64_l(  
   const char *str,  
   _locale_t locale  
);  
__int64 _wtoi64_l(  
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
 각 함수는 입력 문자를 숫자로 해석하여 생성된 `__int64` 값을 반환합니다.  입력이 이 형식의 값으로 변환되지 않는 경우, 반환 값은 `_atoi64` 에 대해 0 입니다.  
  
 큰 양의 정수 값을 사용 하여 오버플로인 경우, 큰 음수 정수 값 오버플로가 발생 할 때 `_atoi64` 는 `I64_MAX` 및 `I64_MIN` 을 반환합니다.  
  
 범위를 벗어난 모든 경우 `errno`는 `ERANGE`로 설정됩니다.  전달된 매개 변수가 `NULL`이 되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명과 같이 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL`로 설정하고 0을 반환합니다.  
  
## 설명  
 이러한 함수는 문자열을 64비트 정수 값으로 변환합니다.  
  
 입력 문자열은 지정한 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다.  함수는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중단합니다.  이 문자는 문자열을 종결하는 null 문자\('\\0' 또는 L'\\0'\)일 수 있습니다.  
  
 `_atoi64`의 `str` 인수 형식은 다음과 같습니다.  
  
```  
[whitespace] [sign] [digits]]  
```  
  
 `whitespace`는 무시되는 공백이나 탭 문자로 구성되며 `sign`은 더하기\(\+\) 또는 빼기\(–\)이며 `digits`는 하나 이상의 숫자입니다.  
  
 `_wtoi64`은 매개 변수로 와이드 문자열을 사용한다는 점을 제외하고 `_atoi64`과 동일합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tstoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
|`_ttoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_atoi64`, `_atoi64_l`|\<stdlib.h\>|  
|`_wtoi64`, `_wtoi64_l`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
## 예제  
 이 프로그램은 `_atoi64` 함수를 사용하여 문자로 저장된 수가 숫자 값으로 변환되는 것을 보여 줍니다.  
  
```  
// crt_atoi64.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the _atoi64 functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    __int64 value = 0;  
  
    // An example of the _atoi64 function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Function: \_atoi64\( "  \-2309 " \) \= \-2309**  
**Function: \_atoi64\( "314127.64" \) \= 314127**  
**Function: \_atoi64\( "3336402735171707160320" \) \= \-1**  
**오버플로 조건이 발생했습니다.**   
## 해당 .NET Framework 항목  
  
-   [System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx)  
  
-   [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)