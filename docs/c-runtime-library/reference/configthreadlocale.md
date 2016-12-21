---
title: "_configthreadlocale | Microsoft Docs"
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
  - "_configthreadlocale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_configthreadlocale"
  - "configthreadlocale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_configthreadlocale 함수"
  - "configthreadlocale 함수"
  - "로캘, 스레드별"
  - "스레드별 로캘"
  - "스레드 로캘"
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _configthreadlocale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드별 로캘 옵션을 구성합니다.  
  
## 구문  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
#### 매개 변수  
 `type`  
 설정할 옵션입니다.  다음 표에 나열된 단계 중 하나를 수행합니다.  
  
## 반환 값  
 스레드별 로캘 이전 상태 \(`_DISABLE_PER_THREAD_LOCALE` 또는 `_ENABLE_PER_THREAD_LOCALE`\), 실패 시\-1을 반환 합니다.  
  
## 설명  
 `_configurethreadlocale` 함수를 사용 하 여 스레드별 로캘 사용 하 여 제어할 수 있습니다.  이러한 옵션 중 하나를 사용하여 스레드별 로캘을 상태를 확인 하거나 지정 하려면:  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 현재 스레드에서 사용 하 여 스레드 관련 로캘을 확인합니다.  이후에 `setlocale` 이 스레드에 스레드 자체의 로케일에 영향을 줍니다.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 현재 스레드에서 전역 로캘을 사용하여 확인 하십시오.  후속 호출을 `setlocale` 이 스레드에서 다른 스레드에서 전역 로캘을 사용하여 적용 합니다.  
  
 `0`  
 이 특정 스레드에 대한 현재 설정을 검색합니다.  
  
 이러한 함수는 `setlocale`, `_tsetlocale`, `_wsetlocale`, `_beginthread`, 그리고 `_beginthreadex`인 동작에 영향을 끼칩니다.  로캘 설정을 다른 메서드를 사용하여 스레드를 만드는 데, 없으면 이러한 스레드에 영향을 주지 않습니다.  
  
 스레드별 로캘을 사용안할 때, 모든 후속 호출을 경우 `setlocale` 또는 `_wsetlocale` 모든 스레드의 로캘이 변경 됩니다.  스레드별 로캘을 사용 하면 `setlocale` 또는 `_wsetlocale` 는 현재 스레드의 로캘을 영향을 받습니다.  
  
 `_configurethreadlocale` 를 스레드별 로캘을 사용하는데 사용하는 경우, `setlocale` 또는 `_wsetlocale` 직후 해당 스레드의 기본 로캘을 설정하는 것을 권고합니다.  
  
 `type` 는 테이블에 나열된 값 중 하나가 아닐 경우,이 함수는 잘못된 매개변수 처리기에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)를 호출합니다.  계속 실행될 경우, 이 함수는 `errno` 을 `EINVAL` 와 \-1로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_configthreadlocale`|\<locale.h\>|  
  
## 예제  
  
```  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using is two independent threads.  
//  
  
#include <locale.h>  
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
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
  
    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI)  
  
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
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
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
  
  **스레드 로캘은 English\_United States.1252로 설정 되었습니다.**  
**영어 로캘의 시간: ' 수요일, 5 월 12 일 '**  
**스레드 로캘은 German\_Germany.1252로 설정 되었습니다.**  
**독일어 로캘을 시간은: ' Mittwoch, 12.  Mai 2004'**    
## 해당 .NET Framework 항목  
 해당 사항 없음. 그러나 [CurrentCulture 속성 사용하기](http://msdn.microsoft.com/ko-kr/3156042d-6082-4205-90b4-c917ae6a3ba6)에서 참조하십시오.  
  
## 참고 항목  
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [다중 스레딩 및 로캘](../../parallel/multithreading-and-locales.md)