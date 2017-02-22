---
title: "qsort_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort_s"
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
  - "qsort_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 정렬"
  - "qsort_s 함수"
  - "빠른 정렬 알고리즘"
  - "배열 정렬"
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# qsort_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빠른 정렬을 수행합니다.  [qsort](../../c-runtime-library/reference/qsort.md) 의 버젼은 보안 향상과 관련된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)로 설명됩니다.  
  
## 구문  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
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
 비교 함수입니다.  첫 번째 인수는 `context` 포인터입니다.  두 번째 인수는 검색을 위한 `key`를 가리키는 포인터입니다.  세 번째 인수는 `key`와 비교하여 배열 요소에 대한 포인터입니다.  
  
 `context`  
 `compare` 루틴의 접근이 필요한 모든 개체가 될 수 있는 컨텍스트를 가리키는 포인터입니다.  
  
## 설명  
 `qsort_s` 함수는 각 `width` 바이트의 `num` 요소의 배열을 정렬하기 위한 빠른 정렬 알고리즘을 구현합니다.  `base` 인수는 정열할 배열의 처음을 가리키는 포인터입니다.  `qsort_s`는 정렬된 요소를 사용하여 이 배열을 덮어씁니다.  이 `compare` 인수는 사용자가 공급한 루틴의 포인터 입니다. 이는 두 배열 요소를 비교하고 그때 그것의 관계를 명시하는 값을 반환합니다.  `qsort_s` 는 각 호출에서 두 배열 원소들에 대한 포인터를 전달하여 정렬하는 동안 `compare` 루틴을 한번 이상 호출합니다.  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 루틴은 반드시 요소를 비교하고 다음 값 중 하나를 반환해야 합니다.  
  
|반환 값|설명|  
|----------|--------|  
|\< 0|`elem1` \< `elem2`|  
|0|`elem2`와 같은 `elem1`|  
|\> 0|`elem1` \> `elem2`|  
  
 비교 함수에 의해 정의된 배열은 오름차순으로 정렬됩니다.  배열을 내림차순으로 정렬하려면, 비교 함수의 "보다 큼" 및 "보다 작음" 조건을 뒤집습니다.  
  
 만일 잘못된 매개변수가 함수에 전달된 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 나타난 것처럼 이 함수는 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 반환합니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
### 오류 조건  
  
|key|base|compare|num|width|errno|  
|---------|----------|-------------|---------|-----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|\<\= 0|`EINVAL`|  
|any|any|`NULL`|any|any|`EINVAL`|  
  
 `qsort_s` 는 `qsort`와 같은 동작을 하지만 `context` 매개 변수를 가지고 `errno`를 설정합니다.  `context` 매개 변수를 전달함으로써, 비교 함수는 개체 기능 또는 요소 포인터를 통해 액세스 할 수 없는 다른 정보에 접근하기 위해서 개체 포인터를 사용할 수 있습니다.  `context`가 `compare` 함수에 사용 가능한 공유 정보를 만들기 위한 정적 변수를 사용하여 도입된 재진입 버그를 방지하기 위해 사용될 수 있기 때문에 `context` 매개 변수의 추가는 `qsort_s`를 더 안전하게 만듭니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`qsort_s`|\<stdlib.h\> 및 \<search.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
 **라이브러리:** 의 모든 버전은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 다음 예제에서는 테이블을 만들 때 `qsort_s` ``  함수에서 `context` 매개 변수를 사용하는 방법을 보여 줍니다.  `context` 매개 변수는 스레드로부터 안전한 정렬의 수행을 쉽게 합니다.  스레드 안전을 보장하기 위해 동기화해야 하는 정적 변수를 사용하는 대신에, 각 정렬에 다른 `context` 매개 변수를 전달합니다.  이 예제에서, 로캘 개체는 `context` 매개 변수로써 사용됩니다.  
  
```  
// crt_qsort_s.cpp  
// compile with: /EHsc /MT  
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4  
// is the n tilde.  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
#define SPANISH_LOCALE "Spanish_Spain.850"  
#define ENGLISH_LOCALE "English_US.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S and \x001f for the n tilde.  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
#define SPANISH_LOCALE "Spanish_Spain.1252"  
#define ENGLISH_LOCALE "English_US.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making sort_array vulnerable to thread  
// conflicts.  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char s1[256];  
    char s2[256];  
    strcpy_s(s1, 256, *(char**)str1);  
    strcpy_s(s2, 256, *(char**)str2);  
    _strlwr_s( s1, sizeof(s1) );  
    _strlwr_s( s2, sizeof(s2) );  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(s1,   
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);  
  
}  
  
void sort_array(char *array[], int num, locale &loc)  
{  
    qsort_s(array, num, sizeof(char*), compare, &loc);  
}  
  
void print_array(char *a[], int c)  
{  
   for (int i = 0; i < c; i++)  
     printf("%s ", a[i]);  
   printf("\n");  
  
}  
  
void sort_german(void * Dummy)  
{  
   sort_array(array1, 6, locale(GERMAN_LOCALE));  
}  
  
void sort_spanish(void * Dummy)  
{     
   sort_array(array2, 3, locale(SPANISH_LOCALE));       
}  
  
void sort_english(void * Dummy)  
{     
   sort_array(array3, 3, locale(ENGLISH_LOCALE));     
}  
  
int main( )  
{  
  
   int i;  
   HANDLE threads[3];  
  
   printf("Unsorted input:\n");  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
   // Create several threads that perform sorts in different  
   // languages at the same time.   
  
   threads[0] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_german , 0, NULL));  
   threads[1] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_spanish, 0, NULL));  
   threads[2] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_english, 0, NULL));  
  
   for (i = 0; i < 3; i++)  
   {  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
      {  
         printf("Error creating threads.\n");  
         exit(1);  
      }  
   }  
  
   // Wait until all threads have terminated.  
   WaitForMultipleObjects(3, threads, true, INFINITE);  
  
   printf("Sorted output: \n");  
  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
}  
```  
  
## 샘플 출력  
  
```  
Unsorted input:  
weiß weis annehmen weizen Zeit weit   
Español España espantado   
table tableux tablet   
Sorted output:   
annehmen weiß weis weit weizen Zeit   
España Español espantado   
table tablet tableux  
```  
  
## 해당 .NET Framework 항목  
 <xref:System.Collections.ArrayList.Sort%2A>  
  
## 참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)