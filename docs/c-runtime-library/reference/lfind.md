---
title: "lfind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lfind"
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
  - "lfind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lfind 함수"
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _lfind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 키에 대한 선형 검색을 수행합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md) 를 참조하십시오.  
  
## 구문  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### 매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색 데이터 베이스에 대한 포인터입니다.  
  
 `num`  
 배열 요소의 수입니다.  
  
 `width`  
 배열 요소의 너비입니다.  
  
 `compare`  
 비교 루틴에 대한 포인터입니다.  첫 번째 매개 변수는 검색에 대한 키에 대한 포인터입니다.  두 번째 매개 변수는 키와 비교하여 배열 요소에 대한 포인터입니다.  
  
## 반환 값  
 만일 키가 파악된 경우, `_lfind` 는 `base` 에서 배열의 요소에 대한 포인터를 반환합니다. 이는 `key`와 매치됩니다.  키가 없는 경우 `_lfind` 는 `NULL`을 반환합니다.  
  
## 설명  
 이 `_lfind` 함수는 `key` 값을 위한 선형 검색을 `num` 요소에 대하여 실행합니다. 이는 각각 `width` 바이트입니다.  이 `bsearch` 와 달리, `_lfind` 는 배열이 저장되는 것을 필요로 하지 않습니다.  이 `base` 인수는 검색할 배열의 기초인 포인터입니다.  이 `compare` 인수는 사용자가 공급한 루틴의 포인터 입니다. 이는 두 배열 요소를 비교하고 그때 그것의 관계를 명시하는 값을 반환합니다.  `_lfind` 는 각 호출에서 두 배열 원소들에 대한 포인터를 전달하여 검색하는 동안 `compare` 루틴을 한번 이상 호출합니다.  이 `compare` 루틴은 요소를 비교하고, 그때, 요소를 0이 아니니 것으로 반환하거나\(요소가 다르단 의미\) 0을\(요소가 동일하단 의미\) 반환합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  `compare` 의 경우, `key` 또는 `num` 이 `NULL` 이거나 `base` 이 NULL이고, \*`num` 인 경우 또는 `width` 이 0보다 더 적은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서처럼 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_lfind`|\<검색\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
  **Hello를 발견했습니다.**   
## 해당 .NET Framework 항목  
 [System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)  
  
## 참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)