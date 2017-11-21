---
title: qsort_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: qsort_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords: qsort_s
dev_langs: C++
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 834441e90cb6656f308673e8475b1cc2e38fd3a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="qsorts"></a>qsort_s
빠른 정렬을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안이 향상된 [qsort](../../c-runtime-library/reference/qsort.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `base`  
 대상 배열의 시작 부분입니다.  
  
 `num`  
 요소의 배열 크기입니다.  
  
 `width`  
 요소 크기(바이트)입니다.  
  
 `compare`  
 비교 함수입니다. 첫 번째 인수는 `context` 포인터입니다. 두 번째 인수는 검색 `key` 에 대한 포인터입니다. 세 번째 인수는 `key`와 비교할 배열 요소에 대한 포인터입니다.  
  
 `context`  
 컨텍스트에 대한 포인터로, `compare` 루틴이 액세스해야 하는 모든 개체일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `qsort_s`함수는 빠른 정렬 알고리즘을 구현하여 `num` 요소(각각 `width`바이트)의 배열을 정렬합니다. `base` 인수는 정렬할 배열의 밑에 대한 포인터입니다. `qsort_s`는 정렬된 요소로 이 배열을 덮어씁니다. `compare` 인수는 두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다. `qsort_s`는 정렬 중에 `compare` 루틴을 한 번 이상 호출하며 각 호출에서 두 배열 요소에 포인터를 전달합니다.  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 루틴은 요소를 비교한 후에 다음 값 중 하나를 반환해야 합니다.  
  
|반환 값|설명|  
|------------------|-----------------|  
|< 0|`elem1`이 `elem2`보다 짧음|  
|0|`elem1`이 `elem2`와 같음|  
|> 0|`elem1` > `elem2`|  
  
 비교 함수에 정의된 대로 배열은 오름차순으로 정렬됩니다. 배열을 내림차순으로 정렬하려면 비교 함수에서 "보다 큼"과 "보다 작음"의 의미를 반전하면 됩니다.  
  
 함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수가 반환되고 `errno`가 `EINVAL`로 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
### <a name="error-conditions"></a>오류 조건  
  
|key|base|compare|num|너비|errno|  
|---------|----------|-------------|---------|-----------|-----------|  
|`NULL`|모두|모두|모두|모두|`EINVAL`|  
|모두|`NULL`|모두|!= 0|모두|`EINVAL`|  
|모두|모두|모두|any|<= 0|`EINVAL`|  
|모두|모두|`NULL`|모두|모두|`EINVAL`|  
  
 `qsort_s`의 경우 동작은 `qsort`와 동일하지만 `context` 매개 변수를 포함하며 `errno`를 설정합니다. `context` 매개 변수를 전달하면 비교 함수가 개체 포인터를 사용하여 요소 포인터를 통해서는 액세스할 수 없는 기타 정보나 개체 기능에 액세스할 수 있습니다. 추가 `context` 매개 변수를 사용 하면 `qsort_s` 되므로 더욱 안전한 `context` 는 공유 정보를 사용할 수 있도록 정적 변수를 사용 하 여 도입 하는 재진입 버그를 방지 하는 데 사용할 수는 `compare` 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`qsort_s`|\<stdlib.h> 및 \<search.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
 **라이브러리:** 모든 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 `context` 에서 매개 변수는 `qsort_s` 함수입니다. `context` 매개 변수를 사용하면 스레드로부터 안전한 정렬을 보다 쉽게 수행할 수 있습니다. 스레드 보안을 유지하기 위해 동기화해야 하는 정적 변수를 사용하는 대신 각 정렬에서 다른 `context` 매개 변수를 전달합니다. 이 예제에서는 로캘 개체가 `context` 매개 변수로 사용됩니다.  
  
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
  
## <a name="sample-output"></a>샘플 출력  
  
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
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)