---
title: "rand | Microsoft Docs"
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
  - "rand"
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
  - "rand"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "의사 난수 생성"
  - "숫자, 의사 난수 생성"
  - "숫자, 의사 난수"
  - "의사 난수"
  - "rand 함수"
  - "난수, 생성"
ms.assetid: 75d9df25-7aaf-4a88-b940-2775559634e8
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

의사 난수를 생성합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [rand\_s](../../c-runtime-library/reference/rand-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
int rand( void );  
```  
  
## 반환 값  
 `rand`는 위에서 설명한 대로 의사 난수를 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `rand` 함수는 0에서 `RAND_MAX` \(32767\) 사이의 의사 난수 정수를 반환합니다.  `rand`의 호출 전 의사 난수 생성기를 시드하기 위해서는 [srand](../../c-runtime-library/reference/srand.md) 함수를 사용합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`rand`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_rand.c  
// This program seeds the random-number generator  
// with the time, then exercises the rand function.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
void SimpleRandDemo( int n )  
{  
   // Print n random numbers.  
   int i;  
   for( i = 0; i < n; i++ )  
      printf( "  %6d\n", rand() );  
}  
  
void RangedRandDemo( int range_min, int range_max, int n )  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   int i;  
   for ( i = 0; i < n; i++ )  
   {  
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min;  
      printf( "  %6d\n", u);  
   }  
}  
  
int main( void )  
{  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   SimpleRandDemo( 10 );  
   printf("\n");  
   RangedRandDemo( -100, 100, 10 );  
}  
```  
  
  **22036**  
 **18330**  
 **11651**  
 **27464**  
 **18093**  
 **3284**  
 **11785**  
 **14686**  
 **11447**  
 **11285**  
 **74**  
 **48**  
 **27**  
 **65**  
 **96**  
 **64**  
 **\-5**  
 **\-42**  
 **\-55**  
 **66**   
## 해당 .NET Framework 항목  
 [System::Random 클래스](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)   
 [rand\_s](../../c-runtime-library/reference/rand-s.md)