---
title: "_set_output_format | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_output_format"
apilocation: 
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_output_format"
  - "_set_output_format"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_output_format 함수"
  - "_TWO_DIGIT_EXPONENT 상수"
  - "출력 서식"
  - "set_output_format 함수"
  - "TWO_DIGIT_EXPONENT 상수"
ms.assetid: 1cb48df8-44b4-4400-bd27-287831d6b3ff
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _set_output_format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 지정된 I\/O 함수에서 사용되는 출력 형식을 사용자 지정합니다.  
  
> [!IMPORTANT]
>  이 함수는 사용되지 않습니다. Visual Studio 2015부터 CRT에서 사용할 수 없습니다.  
  
## 구문  
  
```  
unsigned int _set_output_format(  
   unsigned int format  
);  
```  
  
#### 매개 변수  
 \[in\] `format`  
 사용할 형식을 나타내는 값입니다.  
  
## 반환 값  
 이전 출력 형식입니다.  
  
## 설명  
 `_set_output_format`은 [printf\_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)와 같은 형식이 지정된 I\/O 함수의 출력을 구성하는 데 사용됩니다. 현재, 이 함수에 의해 변경될 수 있는 형식 규칙은 부동 소수점 숫자의 출력에서 지수에 표시되는 자릿수뿐입니다.  
  
 기본적으로 `printf_s`, `wprintf_s` 및 Visual C\+\+ 표준 C 라이브러리의 관련 함수와 같은 함수에 의한 부동 소수점 숫자의 출력은 지수의 값을 나타내는 데 세 자리 숫자가 필요하지 않은 경우에도 지수에 대해 세 자리 숫자를 출력합니다. 0을 사용하여 값을 3자리까지 채웁니다.`_set_output_format`을 사용하면 지수의 크기에 따라 세 번째 숫자가 필요한 경우가 아닌 한 지수에 두 자리 숫자만 인쇄되도록 이 동작을 변경할 수 있습니다.  
  
 두 자리 지수를 사용하도록 설정하려면 예제와 같이 `_TWO_DIGIT_EXPONENT` 매개 변수를 사용하여 이 함수를 호출합니다. 두 자리 지수를 사용하지 않도록 설정하려면 인수 0을 사용하여 이 함수를 호출합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_output_format`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 예제  
  
```  
// crt_set_output_format.c #include <stdio.h> void printvalues(double x, double y) { printf_s("%11.4e %11.4e\n", x, y); printf_s("%11.4E %11.4E\n", x, y); printf_s("%11.4g %11.4g\n", x, y); printf_s("%11.4G %11.4G\n", x, y); } int main() { double x = 1.211E-5; double y = 2.3056E-112; unsigned int old_exponent_format; // Use the default format printvalues(x, y); // Enable two-digit exponent format old_exponent_format = _set_output_format(_TWO_DIGIT_EXPONENT); printvalues(x, y); // Disable two-digit exponent format _set_output_format( old_exponent_format ); printvalues(x, y); }  
```  
  
```Output  
1.2110e-005 2.3056e-112 1.2110E-005 2.3056E-112 1.211e-005  2.306e-112 1.211E-005  2.306E-112 1.2110e-05 2.3056e-112 1.2110E-05 2.3056E-112 1.211e-05  2.306e-112 1.211E-05  2.306E-112 1.2110e-005 2.3056e-112 1.2110E-005 2.3056E-112 1.211e-005  2.306e-112 1.211E-005  2.306E-112  
```  
  
## 참고 항목  
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf 형식 필드 문자](../c-runtime-library/printf-type-field-characters.md)   
 [\_get\_output\_format](../c-runtime-library/get-output-format.md)