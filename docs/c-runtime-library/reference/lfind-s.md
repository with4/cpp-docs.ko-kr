---
title: "_lfind_s | Microsoft Docs"
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
  - "_lfind_s"
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
  - "lfind_s"
  - "_lfind_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lfind_s 함수"
  - "배열[CRT], 검색"
  - "keys, 배열에서 찾기"
  - "lfind_s 함수"
  - "선형 검색"
  - "검색, 선형"
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lfind_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 키에 대한 선형 검색을 수행합니다.  [\_lfind](../../c-runtime-library/reference/lfind.md) 의 버젼은 보안 향상과 관련된[CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)로 설명됩니다.  
  
## 구문  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### 매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색 데이터 베이스에 대한 포인터입니다.  
  
 `num`  
 배열 요소의 수입니다.  
  
 `size`  
 바이트에서 배열 요소의 크기입니다.  
  
 `compare`  
 비교 루틴에 대한 포인터입니다.  첫 번째 매개 변수는 `context` 포인터입니다.  두 번째 매개 변수는 검색에 대한 키에 대한 포인터입니다.  세 번째 매개 변수는 키와 비교하여 배열 요소에 대한 포인터입니다.  
  
 `context`  
 비교 함수에 접근할 수 있는 개체에 대한 포인터입니다.  
  
## 반환 값  
 만일 키가 파악된 경우, `_lfind_s` 는 `base` 에서 배열의 요소에 대한 포인터를 반환합니다. 이는 `key`와 매치됩니다.  키가 없는 경우 `_lfind_s` 는 `NULL`을 반환합니다.  
  
 만일 잘못된 매개변수가 함수에 전달된 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 나타난 것처럼 이 함수는 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  
  
### 오류 조건  
  
|key|base|compare|num|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|0|`EINVAL`|  
|any|any|`NULL`|입니다.|any|`EINVAL`|  
  
## 설명  
 이 `_lfind_s` 함수는 `key` 값을 위한 선형 검색을 `num` 요소에 대하여 실행합니다. 이는 각각 `width` 바이트입니다.  이 `bsearch_s` 와 달리, `_lfind_s` 는 배열이 저장되는 것을 필요로 하지 않습니다.  이 `base` 인수는 검색할 배열의 기초인 포인터입니다.   이 `compare` 인수는 사용자가 공급한 루틴의 포인터 입니다. 이는 두 배열 요소를 비교하고 그때 그것의 관계를 명시하는 값을 반환합니다.  `_lfind_s` 는 `compare` 루틴 또는 검색하는 동안 더 많은 시간을 호출합니다, `context` 포인터와 두 배열 요소 각각의 포인터들을 호출합니다.  이 `compare` 루틴은 요소를 비교하고, 그때, 요소를 0이 아니니 것으로 반환하거나\(요소가 다르단 의미\) 0을\(요소가 동일하단 의미\) 반환합니다.  
  
 `_lfind_s` 는 `_lfind` 와 유사합니다. 이는 부가적인 비교 함수의 인수와 함수의 매개변수 목록인 `context` 포인터를 제외합니다.  이 `context` 포인터는 매우 유용합니다. 만일 검색된 데이터 구조는 개체의 파트일 경우, `compare` 함수는 개체 멤버에 접근할 필요가 있습니다.  이 `compare` 함수는 보이드 포인터를 적절한 개체 형식에 캐스팅할 수 있고, 객체의 멤버에 접근할 수 있습니다.  이 `context` 매개변수의 추가는 `_lfind_s` 를 더욱더 안전하게 만듭니다. 왜냐하면 추가적인 컨텍스트는 재진입 버그들을 피할 수 있습니다. 이는 `compare` 함수를 데이터가 사용할 수 있게 만드는 정적 변수를 사용하는 것과 연관되어 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_lfind_s`|\<검색\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
  **weit 발견**   
## 해당 .NET Framework 항목  
 <xref:System.Collections.ArrayList.Contains%2A>  
  
## 참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort\_s](../../c-runtime-library/reference/qsort-s.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)