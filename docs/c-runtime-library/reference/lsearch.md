---
title: "_lsearch | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch"
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
  - "_lsearch"
  - "lsearch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lsearch 함수"
  - "배열[CRT], 검색"
  - "keys, 배열에서 찾기"
  - "선형 검색"
  - "lsearch 함수"
  - "검색, 선형"
  - "값, 검색"
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값을 찾는 선형 검색을 수행합니다. 찾을 수 없는 경우 목록의 끝에 추가합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)를 참조하십시오.  
  
## 구문  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### 매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색될 기본 배열을 가리키는 포인터입니다.  
  
 `num`  
 요소 수 입니다.  
  
 `width`  
 각 배열 요소의 너비입니다.  
  
 `compare`  
 비교 루틴을 가리키는 포인터입니다.  첫 번째 매개 변수는 검색에 대한 키를 가리키는 포인터입니다.  두 번째 매개 변수는 키와 비교된 배열 요소를 가리키는 포인터입니다.  
  
## 반환 값  
 만일 키가 파악된 경우, `_lsearch` 는 `base` 에서 배열의 요소에 대한 포인터를 반환합니다. 이는 `key`와 매치됩니다.  키가 발견되지 않으면, `_lsearch`는 배열의 끝에 새롭게 추가된 항목을 가리키는 포인터를 반환합니다.  
  
## 설명  
 이 `_lsearch` 함수는 `key` 값을 위한 선형 검색을 `num` 요소에 대하여 실행합니다. 이는 각각 `width` 바이트입니다.  이 `bsearch` 와 달리, `_lsearch` 는 배열이 저장되는 것을 필요로 하지 않습니다.  `key`가 발견되지 않으면, `_lsearch`는 그것을 배열의 끝에 추가하고 `num`을 증가시킵니다.  
  
 이 `compare` 인수는 사용자가 공급한 루틴의 포인터입니다. 이는 두 배열 요소를 비교하고 그때 그것의 관계를 명시하는 값을 반환합니다.  `_lsearch` 는 각 호출에서 두 배열 원소들에 대한 포인터를 전달하여 검색하는 동안 `compare` 루틴을 한번 이상 호출합니다.  이 `compare` 루틴은 요소를 비교하고, 0이 아닌 값을 반환하거나\(요소가 다르단 의미\) 0을\(요소가 동일하단 의미\) 반환합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  `compare` 의 경우, `key` 또는 `num` 이 `NULL` 이거나 `base` 이 NULL이고, \*`num` 인 경우 또는 `width` 이 0보다 더 적은 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에서처럼 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_lsearch`|\<search.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
  **wordlist before \_lsearch: hello thanks bye**  
**wordlist after \_lsearch: hello thanks bye extra**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)