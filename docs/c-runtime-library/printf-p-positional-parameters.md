---
title: "printf_p 위치 매개 변수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_printf_p 함수, 위치 매개 변수"
  - "printf_p 함수, 위치 매개 변수"
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# printf_p 위치 매개 변수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

위치 매개 변수를 사용하면 형식 문자열의 필드로 대체되는 인수의 기준 숫자를 지정할 수 있습니다.  다음 위치 매개 변수 `printf` 함수를 사용할 수 있습니다.  
  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)  
  
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)  
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)  
  
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)  
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)  
  
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)  
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)  
  
 [vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
 [\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)  
  
 [vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)  
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)  
  
 [vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)  
 [\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)  
  
## 위치 매개 변수 지정  
  
##### 매개 변수 인덱스  
 기본적으로 위치 함수는 위치 서식이 없는 경우 위치 매개 변수가 아닌 매개 변수와 동일하게 동작합니다.  위치 매개 변수는 "`%m$x`" 형식으로 지정됩니다. 여기서 `m`은 매개 변수 목록에서 서식 문자열에 선행하는 매개 변수의 위치를 나타내는 서수이고  `x`는 `printf` 함수에 지정된 형식 필드 문자 유형을 나타냅니다.  목록의 매개 변수는 목록의 첫 번째 요소에 해당하는 값 1에서 시작됩니다.  형식 필드 문자에 관한 추가 정보는 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)를 참조하세요.  
  
 이 동작의 예:  
  
```  
_printf_p("%1$s %2$s", "November", "10");  
```  
  
 가 인쇄됩니다.  
  
```  
November 10  
```  
  
 사용되는 숫자의 순서는 지정된 인수의 순서와 일치할 필요가 없습니다.  따라서 다음이 유효합니다.  
  
```  
_printf_p("%2$s %1$s", "November", "10");  
```  
  
 가 인쇄됩니다.  
  
```  
10 November  
```  
  
 기존의 형식 문자열과 달리 서식 지정 중 매개 변수가 한 번 이상 사용될 수 있습니다. 따라서  
  
```  
_printf_p("%1$d times %1$d is %2$d", 10, 100);  
```  
  
 가 인쇄됩니다.  
  
```  
10 times 10 is 100  
```  
  
 모든 인수를 형식 문자열에서 한 번 이상 사용해야 합니다.  
  
 형식 문자열에 허용되는 위치 매개 변수의 최대 수는 `_ARGMAX`로 지정합니다.  
  
##### 너비 및 정밀도  
 인수에서 너비 또는 정밀도를 확인할지 지정하는 데 \* 기호가 사용되는 경우 너비 및 정밀도 값의 위치가 \* 기호 뒤에 바로 표시되어야 합니다.  예를 들면 다음과 같습니다.  
  
```  
_printf_p("%1$*2$s","Hello", 10);  
```  
  
 또는  
  
```  
_printf_p("%2$*1$s",10, "Hello");  
```  
  
##### 위치 인수 및 비 위치 인수 혼합  
 위치 매개 변수는 동일한 형식 문자열에서 비 위치 매개 변수와 함께 혼합할 수 없습니다.  그러나 `printf_p` 및 관련 함수는 비 위치 매개 변수를 포함하는 형식 문자열에서 계속해서 비 위치 매개 변수를 지합니다.  
  
## 예제  
  
```  
// positional_args.c  
// Positional arguments allow the specification of the order  
// in which arguments are consumed in a formatting string.  
  
#include <stdio.h>  
  
int main(int argc, char *argv[])  
{  
    int     i = 1,  
            j = 2,  
            k = 3;  
    double  x = 0.1,  
            y = 0.2,  
            z = 0.3;  
    char    *s1 = "abc",  
            *s2 = "def",  
            *s3 = "ghi";  
  
    // If positional arguments are unspecified,  
    // normal input order is used.  
    _printf_p("%d %d %d\n", i, j, k);  
  
    // Positional args are numbers indicating the  
    // argument enclosed in curly braces.  
    _printf_p("%3$d %1$d %2$d\n", i, j, k);  
  
    // The same positional argument may be reused.  
    _printf_p("%1$d %2$d %1$d\n", i, j);  
  
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);  
  
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);  
}  
```  
  
  **1 2 3**  
**3 1 2**  
**1 2 1**  
**abc def ghi**  
**ghi abc def**   
## 참고 항목  
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)   
 [printf 너비 사양](../c-runtime-library/printf-width-specification.md)   
 [전체 자릿수 사양](../c-runtime-library/precision-specification.md)