---
title: "_configthreadlocale | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _configthreadlocale
- configthreadlocale
dev_langs:
- C++
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1fca01932efb2f80d4aebf94db8900cee5d79805
ms.lasthandoff: 02/24/2017

---
# <a name="configthreadlocale"></a>_configthreadlocale
스레드별 로캘 옵션을 구성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `type`  
 설정할 옵션입니다. 다음 표에 나열된 옵션 중 하나입니다.  
  
## <a name="return-value"></a>반환 값  
 이전 per-thread locale 상태(`_DISABLE_PER_THREAD_LOCALE` 또는 `_ENABLE_PER_THREAD_LOCALE`), 실패 시 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_configurethreadlocale` 함수는 스레드 관련 로캘 사용을 제어하는 데 사용됩니다. 이러한 옵션 중 하나를 사용하여 per-thread locale 상태를 지정하거나 결정할 수 있습니다.  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 현재 스레드에서 스레드 관련 로캘을 사용하도록 합니다. 이 스레드에서 `setlocale`에 대한 후속 호출은 스레드 자체의 로캘에만 영향을 줍니다.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 현재 스레드에서 전역 로캘을 사용하도록 합니다. 이 스레드에서 `setlocale`에 대한 후속 호출은 전역 로캘을 사용하는 다른 스레드에 영향을 줍니다.  
  
 `0`  
 이 특정 스레드에 대한 현재 설정을 검색합니다.  
  
 이러한 함수에의 동작에 영향을 `setlocale`, `_tsetlocale`, 및 `_wsetlocale`합니다. 스레드별 로캘 사용 안 함, 모든 후속 호출을 경우 `setlocale` 또는 `_wsetlocale` 의 전역 로캘을 사용 하는 모든 스레드 로캘을 변경 합니다. per-thread locale이 사용되는 경우 `setlocale` 또는 `_wsetlocale`만 현재 스레드의 로캘에 영향을 줍니다.  
  
 `_configurethreadlocale`을 사용하여 per-thread locale을 사용하도록 설정하는 경우 `setlocale` 또는 `_wsetlocale`을 호출하여 바로 다음 스레드에서 원하는 로캘을 설정할 수 있습니다.  
  
 `type`이 표에 나열된값 중 하나가 아닌 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_configthreadlocale`|\<locale.h>|  
  
## <a name="example"></a>예제  
  
```cpp  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using two independent threads.  
//  
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp 
  
#include <locale.h>  
#include <mbctype.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date and time in the current  
// locale's format.  
int get_time(unsigned char* str)  
{  
    __time64_t  ltime;  
    struct tm   thetime;  
  
    // Retieve the time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // using %#x is the long date representation,  
    // appropriate to the current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm*)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to German  
// and prints the time.  
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )  
{  
    unsigned char str[BUFF_SIZE];  
  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  

    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI);  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "German"));  
  
    // Retrieve the time string from the helper function  
    if (get_time(str) == 0)  
    {  
        printf("The time in German locale is: '%s'\n", str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread spawns a second thread (above) and then  
// sets the locale to English and prints the time.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Enable per-thread locale causes all subsequent locale   
    // setting changes in this thread to only affect this thread.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Retrieve the time string from the helper function  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "English"));  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      NULL, 0, &threadID );  
  
    if (get_time(str) == 0)  
    {  
        // Retrieve the time string from the helper function  
        printf("The time in English locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
} 
```  
  
```Output  
The thread locale is now set to English_United States.1252.  
The time in English locale is: 'Wednesday, May 12, 2004'  
  
The thread locale is now set to German_Germany.1252.  
The time in German locale is: 'Mittwoch, 12. Mai 2004'  
```  
  
## <a name="see-also"></a>참고 항목  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [다중 스레딩 및 로캘](../../parallel/multithreading-and-locales.md)  

