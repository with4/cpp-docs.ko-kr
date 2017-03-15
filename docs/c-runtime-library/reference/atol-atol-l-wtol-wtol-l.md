---
title: "atol, _atol_l, _wtol, _wtol_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atol"
  - "_wtol_l"
  - "_wtol"
  - "_atol_l"
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
  - "_atol_l"
  - "_ttol_l"
  - "_tstol_l"
  - "_tstol"
  - "_wtol"
  - "_ttol"
  - "_wtol_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tstol 함수"
  - "atol 함수"
  - "ttol 함수"
  - "_atol_l 함수"
  - "_tstol_l 함수"
  - "문자열 변환, 정수로"
  - "_tstol 함수"
  - "_ttol 함수"
  - "_ttol_l 함수"
  - "atol_l 함수"
  - "wtol_l 함수"
  - "_wtol_l 함수"
  - "wtol 함수"
  - "_wtol 함수"
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# atol, _atol_l, _wtol, _wtol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

long 정수로 문자열을 변환합니다.  
  
## 구문  
  
```  
long atol(  
   const char *str   
);  
long _atol_l(  
   const char *str,  
   _locale_t locale  
);  
long _wtol(  
   const wchar_t *str   
);  
long _wtol_l(  
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
 각 함수는 입력 문자를 숫자로 해석하여 생성된 `long` 값을 반환합니다.  만일 입력을 해당 형식의 값으로 변환할 수 없을 경우, 반환값은 `atol` 에 의해 0L입니다.  
  
 큰 양의 정수 값을 사용 하여 오버플로인 경우, `atol` 는 `LONG_MAX` 을 반환합니다; 큰 음수 정수 값 오버플로가 발생 할 때, `LONG_MIN` 을 반환합니다.  범위를 벗어난 모든 경우 `errno`는 `ERANGE`로 설정됩니다.  전달된 매개 변수가 `NULL`이 되는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명과 같이 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL`로 설정하고 0을 반환합니다.  
  
## 설명  
 이러한 함수는 문자열을 long 정수 값\(`atol`\) 로 변환합니다.  
  
 입력 문자열은 지정한 형식의 숫자 값으로 해석될 수 있는 문자 시퀀스입니다.  함수는 숫자 부분으로 인식할 수 없는 첫 번째 문자에서 입력 문자열 읽기를 중단합니다.  이 문자는 문자열을 종결하는 `NULL` 문자\('\\0' 또는 L'\\0'\)일 수 있습니다.  
  
 `atol`의 `str` 인수 형식은 다음과 같습니다.  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace`는 무시되는 공백이나 탭 문자로 구성되며 `sign`은 더하기\(\+\) 또는 빼기\(–\)이며 `digits`는 하나 이상의 숫자입니다.  
  
 `_wtol`은 와이드 문자열을 사용한다는 점을 제외하고 `atol`과 동일합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_tstol`|`atol`|`atol`|`_wtol`|  
|`_ttol`|`atol`|`atol`|`_wtol`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`atol`|\<stdlib.h\>|  
|`_atol_l`, `_wtol`, `_wtol_l`|\<\<stdlib.h\>\> 또는 \<\<wchar.h\>\>|  
  
## 예제  
 이 프로그램은 `atol` 함수를 사용하여 문자로 저장된 수가 숫자 값으로 변환되는 것을 보여 줍니다.  
  
```  
// crt_atol.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the atol functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    long    value = 0;  
  
    // An example of the atol function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **함수: atol\( "  \-2309 " \) \= \-2309**  
**함수: atol\( "314127.64" \) \= 314127**  
**함수: atol\( "3336402735171707160320" \) \= 2147483647**  
**오버플로 조건이 발생했습니다.**   
## 해당 .NET Framework 항목  
  
-   [System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)  
  
-   [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)