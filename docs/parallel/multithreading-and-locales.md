---
title: "다중 스레딩 및 로캘 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "로캘[C++], 다중 스레딩"
  - "다중 스레딩[C++], 로캘"
  - "스레드별 로캘"
  - "스레딩[C++], 로캘"
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 다중 스레딩 및 로캘
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C 런타임 라이브러리와 표준 C\+\+ 라이브러리에서는 모두 프로그램 로캘을 변경하는 기능을 제공합니다.  이 항목에서는 다중 스레드 응용 프로그램에서 두 라이브러리의 로캘 기능을 사용할 때 발생하는 문제에 대해 설명합니다.  
  
## 설명  
 C 런타임 라이브러리에서는 `_beginthread`와 `_beginthreadex` 함수를 사용하여 다중 스레드 응용 프로그램을 만들 수 있습니다.  이 항목에서는 이들 함수를 사용하여 만든 다중 스레드 응용 프로그램에 대해서만 설명합니다.  자세한 내용은 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)을 참조하십시오.  
  
 C 런타임 라이브러리를 사용하여 로캘을 변경하려면 [setlocale](../preprocessor/setlocale.md) 함수를 사용합니다.  이전 버전의 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]에서 이 함수는 항상 전체 응용 프로그램에 걸쳐 로캘을 수정했습니다.  이제는 스레드 단위로 로캘을 설정하는 기능이 지원됩니다.  이는 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 함수를 통해 수행됩니다.  [setlocale](../preprocessor/setlocale.md)에서 현재 스레드의 로캘만 변경하도록 지정하려면 이 스레드에서 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`을 호출합니다.  반대로 `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)`을 호출하면 이 스레드에서 전역 로캘을 사용하게 되고, 이 스레드에서 [setlocale](../preprocessor/setlocale.md)을 호출하면 스레드별 로캘을 명시적으로 사용하지 않는 모든 스레드의 로캘이 변경됩니다.  
  
 C\+\+ 런타임 라이브러리를 사용하여 로캘을 변경하려면 [locale 클래스](../standard-library/locale-class.md)를 사용합니다.  [locale::global](../Topic/locale::global.md) 메서드를 호출하여 스레드별 로캘을 명시적으로 사용하지 않는 모든 스레드의 로캘을 변경할 수 있습니다.  단일 스레드 또는 응용 프로그램 일부의 로캘을 변경하려면 해당 스레드 또는 코드 부분에서 `locale` 개체의 인스턴스를 만들기만 하면 됩니다.  
  
> [!NOTE]
>  [locale::global](../Topic/locale::global.md)을 호출하면 표준 C\+\+ 라이브러리 및 C 런타임 라이브러리 모두의 로캘이 변경됩니다.  그러나 [setlocale](../preprocessor/setlocale.md)을 호출하면 C 런타임 라이브러리의 로캘만 변경되고 표준 C\+\+ 라이브러리는 영향을 받지 않습니다.  
  
 다음 예제에서는 [setlocale](../preprocessor/setlocale.md) 함수, [locale 클래스](../standard-library/locale-class.md) 및 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 함수를 사용하여 여러 가지 다양한 시나리오에서 응용 프로그램의 로캘을 변경하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서 주 스레드는 두 개의 자식 스레드를 생성합니다.  첫 번째 스레드인 A 스레드에서는 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`을 호출하여 스레드별 로캘을 사용합니다.  두 번째 스레드인 B 스레드에서는 주 스레드와 마찬가지로 스레드별 로캘을 사용하지 않습니다.  그런 다음 A 스레드에서는 C 런타임 라이브러리의 [setlocale](../preprocessor/setlocale.md) 함수를 사용하여 로캘을 변경합니다.  
  
 A 스레드에서는 스레드별 로캘을 사용하므로 A 스레드의 C 런타임 라이브러리 함수에서만 "french" 로캘을 사용하기 시작합니다.  B 스레드와 주 스레드의 C 런타임 라이브러리 함수에서는 계속 "C" 로캘을 사용합니다.  또한 [setlocale](../preprocessor/setlocale.md)은 표준 C\+\+ 라이브러리 로캘에 영향을 주지 않으므로 모든 표준 C\+\+ 라이브러리 개체에서는 계속 "C" 로캘을 사용합니다.  
  
```  
// multithread_locale_1.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[A 스레드\] 스레드당 로캘이 설정되어 있습니다.**  
**\[스레드 A\] CRT 로캘이 "French\_France.1252"로 설정**  
**\[스레드 A\] 로캘::전체가 "C"로 설정**  
**\[B 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 B\] CRT 로캘이 "C"로 설정**  
**\[스레드 B\] 로캘::전체가 "C"로 설정**  
**\[메인 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 기본\] CRT 로캘이 "C"로 설정**  
**\[스레드 기본\] 로캘::전체가 "C"로 설정**   
## 예제  
 이 예제에서 주 스레드는 두 개의 자식 스레드를 생성합니다.  첫 번째 스레드인 A 스레드에서는 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`을 호출하여 스레드별 로캘을 사용합니다.  두 번째 스레드인 B 스레드에서는 주 스레드와 마찬가지로 스레드별 로캘을 사용하지 않습니다.  그런 다음 A 스레드에서는 표준 C\+\+ 라이브러리의 [locale::global](../Topic/locale::global.md) 메서드를 사용하여 로캘을 변경합니다.  
  
 A 스레드에서는 스레드별 로캘을 사용하므로 A 스레드의 C 런타임 라이브러리 함수에서만 "french" 로캘을 사용하기 시작합니다.  B 스레드와 주 스레드의 C 런타임 라이브러리 함수에서는 계속 "C" 로캘을 사용합니다.  그러나 [locale::global](../Topic/locale::global.md) 메서드는 로캘을 "전역"으로 변경하므로 모든 스레드의 모든 표준 C\+\+ 라이브러리 개체에서는 "french" 로캘을 사용하기 시작합니다.  
  
```  
// multithread_locale_2.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[A 스레드\] 스레드당 로캘이 설정되어 있습니다.**  
**\[스레드 A\] CRT 로캘이 "French\_France.1252"로 설정**  
**\[스레드 A\] CRT 로캘::전체가 "French\_France.1252"로 설정**  
**\[B 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 B\] CRT 로캘이 "C"로 설정**  
**\[스레드 B\] 로캘::전체가 "French\_France.1252"로 설정**  
**\[메인 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 기본\] CRT 로캘이 "C"로 설정**  
**\[스레드 기본\] 로캘::전체가 "French\_France.1252"로 설정**   
## 예제  
 이 예제에서 주 스레드는 두 개의 자식 스레드를 생성합니다.  첫 번째 스레드인 A 스레드에서는 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`을 호출하여 스레드별 로캘을 사용합니다.  두 번째 스레드인 B 스레드에서는 주 스레드와 마찬가지로 스레드별 로캘을 사용하지 않습니다.  그런 다음 B 스레드에서는 C 런타임 라이브러리의 [setlocale](../preprocessor/setlocale.md) 함수를 사용하여 로캘을 변경합니다.  
  
 B 스레드에서는 스레드별 로캘을 사용하지 않으므로 B 스레드와 주 스레드의 C 런타임 라이브러리 함수에서는 "french" 로캘을 사용하기 시작합니다.  A 스레드에서는 스레드별 로캘을 사용하므로 A 스레드의 C 런타임 라이브러리 함수에서는 계속 "C" 로캘을 사용합니다.  또한 [setlocale](../preprocessor/setlocale.md)은 표준 C\+\+ 라이브러리 로캘에 영향을 주지 않으므로 모든 표준 C\+\+ 라이브러리 개체에서는 계속 "C" 로캘을 사용합니다.  
  
```  
// multithread_locale_3.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[B 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 B\] CRT 로캘이 "French\_France.1252"로 설정**  
**\[스레드 B\] 로캘::전체가 "C"로 설정**  
**\[A 스레드\] 스레드당 로캘이 설정되어 있습니다.**  
**\[스레드 A\] CRT 로캘이 "C"로 설정**  
**\[스레드 A\] 로캘::전체가 "C"로 설정**  
**\[메인 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 기본\] CRT 로캘이 "French\_France.1252"로 설정**  
**\[스레드 기본\] 로캘::전체가 "C"로 설정**   
## 예제  
 이 예제에서 주 스레드는 두 개의 자식 스레드를 생성합니다.  첫 번째 스레드인 A 스레드에서는 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`을 호출하여 스레드별 로캘을 사용합니다.  두 번째 스레드인 B 스레드에서는 주 스레드와 마찬가지로 스레드별 로캘을 사용하지 않습니다.  그런 다음 B 스레드에서는 표준 C\+\+ 라이브러리의 [locale::global](../Topic/locale::global.md) 메서드를 사용하여 로캘을 변경합니다.  
  
 B 스레드에서는 스레드별 로캘을 사용하지 않으므로 B 스레드와 주 스레드의 C 런타임 라이브러리 함수에서는 "french" 로캘을 사용하기 시작합니다.  A 스레드에서는 스레드별 로캘을 사용하므로 A 스레드의 C 런타임 라이브러리 함수에서는 계속 "C" 로캘을 사용합니다.  그러나 [locale::global](../Topic/locale::global.md) 메서드는 로캘을 "전역"으로 변경하므로 모든 스레드의 모든 표준 C\+\+ 라이브러리 개체에서는 "french" 로캘을 사용하기 시작합니다.  
  
```  
// multithread_locale_4.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
  **\[B 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 B\] CRT 로캘이 "French\_France.1252"로 설정**  
**\[스레드 B\] 로캘::전체가 "French\_France.1252"로 설정**  
**\[A 스레드\] 스레드당 로캘이 설정되어 있습니다.**  
**\[스레드 A\] CRT 로캘이 "C"로 설정**  
**\[스레드 A\] CRT 로캘::전체가 "French\_France.1252"로 설정**  
**\[메인 스레드\] 스레드당 로캘이 설정되어 있지 않습니다.**  
**\[스레드 기본\] CRT 로캘이 "French\_France.1252"로 설정**  
**\[스레드 기본\] 로캘::전체가 "French\_France.1252"로 설정**   
## 참고 항목  
 [이전 코드를 위한 다중 스레드 지원\(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [국제화](../c-runtime-library/internationalization.md)   
 [로캘](../c-runtime-library/locale.md)   
 [\<clocale\>](../standard-library/clocale.md)   
 [\<locale\>](../standard-library/locale.md)   
 [locale 클래스](../standard-library/locale-class.md)