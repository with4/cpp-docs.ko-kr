---
title: "_set_printf_count_output | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_printf_count_output"
  - "_set_printf_count_output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%n 형식"
  - "_set_printf_count_output 함수"
  - "set_printf_count_output 함수"
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _set_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 와 비슷한 함수에서 `%n` 서식의 지원여부.  
  
## 구문  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### 매개 변수  
 `enable`  
 `%n` 을 지원하지 않으려면 0을, `%n` 을 지원한다면 0이 아닌 값입니다.  
  
## 속성 값\/반환 값  
 이 함수를 호출하기 전에 `%n` 의 상태를 지원합니다: 만일 `%n` 을 활성화했다면 0이 아닌 수, 만일 이것을 활성화 하지 않는다면 0입니다.  
  
## 설명  
 보안상의 이유로, `%n` 형식 지정자에 대한 지원은 `printf` 와 이것의 변화된 형식들에서 활성화되지 않습니다.  만일 `%n` 이 `printf` 형식 지정에서 발견되는 경우, 기본 동작은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개변수 처리기를 호출하는 것입니다.  0이 아닌 인수를 사용해 `_set_printf_count_output` 를 호출하는 것은 [printf 형식 필드 문자](../../c-runtime-library/printf-type-field-characters.md)에 설명된 대로 `%n` 를 설명하기 위해 `printf`\-와 비슷한 함수를 발생시킵니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_printf_count_output`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
## Output  
  
```  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_get\_printf\_count\_output](../../c-runtime-library/reference/get-printf-count-output.md)