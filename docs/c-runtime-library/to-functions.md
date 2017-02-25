---
title: "to 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "To"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대/소문자, 변환"
  - "문자, 변환"
  - "소문자, 문자열 변환"
  - "문자열 변환, 대/소문자"
  - "문자열 변환, 다른 문자로"
  - "함수"
  - "대문자, 문자열 변환"
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# to 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 **to** 함수의 각각과 그것과 관련된 매크로는 단일 문자를 다른 문자로 전환합니다.  
  
|||  
|-|-|  
|[\_\_toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper, \_toupper, towupper](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|  
|[tolower, \_tolower, towlower](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)||  
  
## 설명  
 이 **to** 함수와 매크로 전환은 다음과 같습니다.  
  
|루틴|매크로|설명|  
|--------|---------|--------|  
|`__toascii`|`__toascii`|`c` 를 ASCII문자로 전환합니다.|  
|`tolower`|`tolower`|적절한 경우, `c` 를 소문자로 전환합니다.|  
|`_tolower`|`_tolower`|`c` 를 소문자로 전환합니다.|  
|`towlower`|없음|`c` 를 해다 와이드 문자 소문자로 전환합니다.|  
|`toupper`|`toupper`|적절한 경우, `c` 를 대문자로 전환합니다.|  
|`_toupper`|`_toupper`|`c` 를 대문자로 전환합니다.|  
|`towupper`|없음|c를 해당하는 와이드 문자 대문자로 전환합니다.|  
  
 매크로에 의해 정의된 **to** 루틴의 함수버젼을 사용하기 위하여, `#undef` 을 사용한 매크로 정의를 제거하거나 CTYPE.H를 포함하지 않습니다.  만일 \/Za 컴파일러 옵션을 사용할 경우, 컴파일러는 `toupper` 또는 `tolower` 인 함수 버전을 사용합니다.  이 `toupper` 와 `tolower` 함수 선언은 STDLIB.H에 있습니다.  
  
 이 `__toascii` 루틴은 7 비트보다 낮은 순서인 `c` 를 0으로 모든 것을 설정하고 그 결과, 전환된 값은 ASCII 문자집합에서 문자를 나타냅니다.  만일 `c` 이미 ASCII 문자를 나타낼 경우, `c` 는 변경되지 않습니다.  
  
 이 `tolower` 와 `toupper` 루틴 :  
  
-   `LC_CTYPE` 범주인 현재 로캘에 따릅니다. \(`tolower` sms `isupper` 을 호출하고 `toupper` 은 `islower` 을 호출합니다.\)  
  
-   `c` 를 전환합니다. 만일 `c` 가 현재 로캘에서 적절한 경우의 전환 가능한 문자를 나타낼 경우와 반대 경우로 다른 로캘이 존재할 경우입니다.  그렇지 않으면 `c` 는 변경 되지 않습니다.  
  
 이 `_tolower` 와 `_toupper` 루틴 :  
  
-   로케일에 관계 없이, 훨씬 더 빠른 버전은 `tolower` 및 **toupper.**  
  
-   사용될 수 있습니다. 오직 **isascii\(**`c`**\)** 및 다른 **isupper\(**`c`**\)** 또는 **islower\(**`c`**\)**, 가 상대적으로 0이 아닐 때 입니다.  
  
-   결과가 정의되지 않습니다. 만일 `c` 가 전환하는 데 있어서 적절한 경우인 ASCII 문자가 아닐 경우입니다.  
  
 이 `towlower` 와 `towupper` 함수는 전환된 `c` 의 복사본을 반환하고 만일 다음 조건을 따르는 두 가지가 0이 아닐 경우 입니다.  그렇지 않으면 `c` 는 변경 되지 않습니다.  
  
-   `c` 는 적절한 사례의 와이드 문자 \(즉, 있는 `iswupper` 또는  **iswlower,** 각각 0이 아닌\).  
  
-   대상 사례의 해당 와이드 문자가 있습니다. \(즉, `iswlower` 또는 **iswupper,** 각각 0이 아닌 경우 입니다\).  
  
## 예제  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
  **일부 문자는 대문자입니다.**  
**이러한 문자는 대문자의 일부입니다.**   
## 참고 항목  
 [데이터 변환](../c-runtime-library/data-conversion.md)   
 [로캘](../c-runtime-library/locale.md)   
 [is, isw 루틴](../c-runtime-library/is-isw-routines.md)