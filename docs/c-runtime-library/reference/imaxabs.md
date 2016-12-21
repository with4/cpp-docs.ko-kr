---
title: "imaxabs | Microsoft Docs"
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
  - "imaxabs"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "imaxabs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "imaxabs 함수"
ms.assetid: de2566a3-1415-4e9a-91b5-7ac3a49ebf5e
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# imaxabs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 크기의 정수의 절대 값을 계산합니다.  
  
## 구문  
  
```  
intmax_t imaxabs(  
   intmax_t n   
);  
```  
  
#### 매개 변수  
 *n*  
 정수 값입니다.  
  
## 반환 값  
 `imaxabs` 함수는 인수의 절대 값을 반환합니다.  반환되는 오류가 없습니다.  
  
> [!NOTE]
>  `intmax_t` 사용으로 표시될 수 있는 음의 정수의 범위가 양의 정수의 범위보가 더 크기 때문에 변환될 수 없는 `imaxabs`에 인수를 제공할 수 있습니다.  인수의 절대 값이 반환 형식으로 표시될 수 없을 경우 `imaxabs`의 행동은 정의되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`imaxabs`|\<inttypes.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_imaxabs.c  
// Build using: cl /W3 /Tc crt_imaxabs.c  
// This example calls imaxabs to compute an  
// absolute value, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x = LLONG_MIN + 2;  
  
   printf("The absolute value of %lld is %lld\n", x, imaxabs(x));  
}  
```  
  
  **\-9223372036854775806의 절대 값은 9223372036854775806입니다.**   
## 해당 .NET Framework 항목  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [abs, labs, llabs \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [labs, llabs](../../misc/labs-llabs.md)