---
title: "__min | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__min"
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
apitype: "DLLExport"
f1_keywords: 
  - "__min"
  - "min"
  - "_min"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__min 매크로"
  - "_min 매크로"
  - "min 매크로"
  - "최소값 매크로"
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# __min
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 값 중 더 작은 값을 반환합니다.  
  
## 구문  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### 매개 변수  
 `type`  
 숫자 데이터 형식  
  
 `a, b`  
 비교 되는 숫자 형식의 값입니다.  
  
## 반환 값  
 두 인수 중 작은입니다.  
  
## 설명  
 `__min` 매크로는 두 값을 비교 하고 더 작은 값을 반환 합니다.  서명 되거나 서명 되지 않은 데이터 형식은 모든 숫자 인수가 될 수 있습니다.  인수와 반환 값은 동일한 데이터 형식 이어야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`__min`|\<stdlib.h\>|  
  
## 예제  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
  **The larger of 10 and 21 is 21**  
**The smaller of 10 and 21 is 10**   
## 해당 .NET Framework 항목  
 [System::Math::Min](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_\_max](../../c-runtime-library/reference/max.md)