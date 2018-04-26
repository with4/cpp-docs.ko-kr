---
title: qsort_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- qsort_s
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
f1_keywords:
- qsort_s
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b325c8efac41513cff097257833244222a84b31
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="qsorts"></a>qsort_s

빠른 정렬을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안이 향상된 [qsort](qsort.md) 버전입니다.

## <a name="syntax"></a>구문

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>매개 변수

*기본* 대상 배열의 시작 합니다.

*숫자* 배열 요소에는 크기입니다.

*너비* 요소 크기 (바이트)입니다.

*비교* 비교 함수입니다. 첫 번째 인수는 *컨텍스트* 포인터입니다. 두 번째 인수가에 대 한 포인터는 *키* 검색 합니다. 세 번째 인수는와 비교할 배열 요소에 포인터 *키*합니다.

*상황에 맞는* 하나일 수 있습니다는 컨텍스트에 대 한 포인터는 개체는 *비교* 루틴에 액세스 해야 합니다.

## <a name="remarks"></a>설명

**qsort_s** 배열을 정렬 하려면 빠른 정렬 알고리즘을 구현 하는 함수 *번호* 의 각 요소 *너비* 바이트입니다. 인수 *기본* 정렬할 배열 로그의에 대 한 포인터입니다. **qsort_s** 이 배열의 정렬된 된 요소를 덮어씁니다. 인수 *비교* 두 배열 요소를 비교 하 고 서로의 관계를 지정 하는 값을 반환 하는 사용자 제공 루틴에 대 한 포인터입니다. **qsort_s** 호출은 *비교* 일상적인 한 번 이상 정렬, 각 호출에 두 개의 배열 요소에 포인터를 전달 하는 동안:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

루틴은 요소를 비교한 후에 다음 값 중 하나를 반환해야 합니다.

|반환 값|설명|
|------------------|-----------------|
|< 0|**elem1** 미만 **elem2**|
|0|**elem1** 같음 **elem2**|
|> 0|**elem1** 보다 큰 **elem2**|

비교 함수에 정의된 대로 배열은 오름차순으로 정렬됩니다. 배열을 내림차순으로 정렬하려면 비교 함수에서 "보다 큼"과 "보다 작음"의 의미를 반전하면 됩니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 함수가 반환 하 고 **errno** 로 설정 된 **EINVAL**합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

### <a name="error-conditions"></a>오류 조건

|key|base|compare|num|너비|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|모두|모두|모두|모두|**EINVAL**|
|모두|**NULL**|모두|!= 0|모두|**EINVAL**|
|모두|모두|모두|any|<= 0|**EINVAL**|
|모두|모두|**NULL**|모두|모두|**EINVAL**|

**qsort_s** 동일한 동작 **qsort** 되었지만 *컨텍스트* 매개 변수 및 집합 **errno**합니다. 전달 하 여 한 *컨텍스트* 매개 변수를 비교 함수 개체 기능 또는 기타 정보를 액세스할 수 없습니다. 요소 포인터를 통해 액세스 하는 개체 포인터를 사용할 수 있습니다. 추가 *컨텍스트* 매개 변수를 사용 하면 **qsort_s** 되므로 더욱 안전한 *컨텍스트* 는 정적 변수를 사용 하 여 도입 하는 재진입 버그를 방지 하는 데 사용할 수 공유를 사용할 수 있는 정보는 *비교* 함수입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> 및 \<search.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 모든 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법을 *컨텍스트* 에서 매개 변수는 **qsort_s** 함수입니다. *컨텍스트* 매개 변수를 사용 하면 보다 쉽게 수행할 스레드로부터 안전한 정렬 합니다. 스레드로부터 안전을 보장 하기 위해 동기화 해야 하는 정적 변수를 사용 하는 대신 다른 전달 *컨텍스트* 각 정렬에 대 한 매개 변수입니다. 이 예제에서는 로캘 개체로 사용 되는 *컨텍스트* 매개 변수입니다.

```cpp
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

### <a name="sample-output"></a>샘플 출력

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>참고자료

[검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
