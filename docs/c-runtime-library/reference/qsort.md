---
title: "qsort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "qsort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "qsort 함수"
  - "빠른 정렬 알고리즘"
  - "배열 정렬"
  - "배열[CRT], 정렬"
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# qsort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빠른 정렬을 수행합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [qsort\_s](../../c-runtime-library/reference/qsort-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### 매개 변수  
 `base`  
 대상 배열의 시작입니다.  
  
 `num`  
 요소의 배열 크기입니다.  
  
 `width`  
 요소 크기\(바이트\)입니다.  
  
 `compare`  
 사용자가 제공한 루틴은 두 개의 배열 요소를 비교하고 그들의 관계를 지정하는 값을 반환하는 포인터입니다.  
  
## 설명  
 `qsort` 함수는 각 `width` 바이트의 `num` 요소의 배열을 정렬하기 위한 빠른 정렬 알고리즘을 구현합니다.  `base` 인수는 정열할 배열의 처음을 가리키는 포인터입니다.  `qsort` 은 정렬된 원소들을 사용하여 이 배열을 덮어씁니다.  
  
 `qsort` 는 각 호출에서 두 배열 원소들에 대한 포인터를 전달하여 정렬하는 동안 `compare` 루틴을 한번 이상 호출합니다.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 루틴은 요소를 비교하고 다음 값 중 하나를 반환합니다.  
  
|함수 반환값을 비교합니다.|설명|  
|--------------------|--------|  
|\< 0|`elem1` \< `elem2`|  
|0|`elem2`와 같은 `elem1`|  
|\> 0|`elem1` \> `elem2`|  
  
 비교 함수에 의해 정의된 배열은 오름차순으로 정렬됩니다.  배열을 내림차순으로 정렬하려면, 비교 함수의 "보다 큼" 및 "보다 작음" 조건을 뒤집습니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  만일 `compare` 또는 `num` 이 `NULL` 이거나 `base` 이 `NULL` 이고 \*`num` 이 0이 아닌 경우, 또는 `width` 이 0보다 더 적은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서 설명된 대로 잘못된 매개변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno` 를 `EINVAL` 로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`qsort`|\<stdlib.h\> 및 \<search.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
  **모든 좋은 가치를 받을만한 사람**   
## 해당 .NET Framework 항목  
 [System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)  
  
## 참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)