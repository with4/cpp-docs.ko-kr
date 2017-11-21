---
title: "다중 스레딩 및 로캘 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e60083aa67cc640dafb5c096b83d3097df04db1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-and-locales"></a>다중 스레딩 및 로캘
C 런타임 라이브러리와 c + + 표준 라이브러리는 프로그램의 로캘 변경을 대 한 지원을 제공 합니다. 이 항목에서는 다중 스레드 응용 프로그램에서 두 라이브러리의 로캘 기능을 사용 하는 경우 발생 하는 문제를 설명 합니다.  
  
## <a name="remarks"></a>설명  
 C 런타임 라이브러리와 함께 사용 하 여 다중 스레드 응용 프로그램을 만들 수 있습니다는 `_beginthread` 및 `_beginthreadex` 함수입니다. 이 항목에서는 이러한 함수를 사용 하 여 생성 하는 다중 스레드 응용 프로그램에 대해서만 다룹니다. 자세한 내용은 참조 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)합니다.  
  
 C 런타임 라이브러리를 사용 하 여 로캘의 변경 하려면 사용 된 [setlocale](../preprocessor/setlocale.md) 함수입니다. 이전 버전의 Visual c + +에서는이 함수는 항상 전체 응용 프로그램에 걸쳐 로캘을 수정 합니다. 스레드 단위 별로 로캘 설정에 대 한 이제 지원이 됩니다. 이렇게 사용 하는 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 함수입니다. 되도록 지정 하려면 [setlocale](../preprocessor/setlocale.md) 로캘은 현재 스레드의 호출에만 변경 해야 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` 스레드에서 합니다. 반대로 호출 `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` 으로 인해 해당 스레드를 사용 하 여 전역 로캘 및를 호출할 때 [setlocale](../preprocessor/setlocale.md) 스레드 로캘을 명시적으로 설정 하지 않은 모든 스레드의 로캘을 변경 됩니다.  
  
 C + + 런타임 라이브러리를 사용 하 여 로캘의 변경 하려면 사용 된 [locale 클래스](../standard-library/locale-class.md)합니다. 호출 하 여는 [locale:: global](../standard-library/locale-class.md#global) 메서드의 스레드 단위 로캘을 명시적으로 사용 하지 않는 모든 스레드의 로캘을 변경 합니다. 단일 스레드 또는 응용 프로그램의 일부의 로캘을 변경 하려면의 인스턴스를 만들기만 `locale` 해당 스레드 또는 코드의 일부에는 개체입니다.  
  
> [!NOTE]
>  호출 [locale:: global](../standard-library/locale-class.md#global) 모두 c + + 표준 라이브러리 및 C 런타임 라이브러리에 대 한 로캘을 변경 합니다. 그러나 호출 [setlocale](../preprocessor/setlocale.md) C 런타임 라이브러리, c + + 표준 라이브러리가 영향을 받지 않습니다에 대 한 로캘을 변경 됩니다.  
  
 다음 예제를 사용 하는 방법을 보여 줍니다는 [setlocale](../preprocessor/setlocale.md) 함수는 [locale 클래스](../standard-library/locale-class.md), 및 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) 함수에서 응용 프로그램의 로캘을 변경 하려면 몇 가지 다른 시나리오입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 주 스레드는 두 개의 하위 스레드를 생성 합니다. 첫 번째 스레드가 스레드 A 스레드별 로캘 호출 하 여 사용 하도록 설정 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`합니다. 두 번째 스레드가, 스레드 B 뿐 아니라 주 스레드 로컬을 사용 하지 마십시오. 그런 다음 A를 사용 하 여 로캘 변경 스레드에서 [setlocale](../preprocessor/setlocale.md) C 런타임 라이브러리의 기능입니다.  
  
 이후 스레드 A는 스레드 단위 로캘을 사용 하 고, "프랑스어" 로캘을 사용 하 여 스레드 A 시작에서 C 런타임 라이브러리 함수에만 합니다. 주 스레드 및 스레드 B에서 C 런타임 라이브러리 함수는 "C" 로캘에서 사용 하 여 계속 합니다. 또한 [setlocale](../preprocessor/setlocale.md) 개체는 계속 "C" 로캘에서 사용 하는 모든 c + + 표준 라이브러리는 c + + 표준 라이브러리 로캘의 영향을 주지 않습니다.  
  
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
  
```Output  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "French_France.1252"  
[Thread A] locale::global is set to "C"  
  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "C"  
[Thread B] locale::global is set to "C"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "C"  
[Thread main] locale::global is set to "C"  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 주 스레드는 두 개의 하위 스레드를 생성 합니다. 첫 번째 스레드가 스레드 A 스레드별 로캘 호출 하 여 사용 하도록 설정 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`합니다. 두 번째 스레드가, 스레드 B 뿐 아니라 주 스레드 로컬을 사용 하지 마십시오. 그런 다음 A를 사용 하 여 로캘 변경 스레드에서 [locale:: global](../standard-library/locale-class.md#global) c + + 표준 라이브러리의 메서드.  
  
 이후 스레드 A는 스레드 단위 로캘을 사용 하 고, "프랑스어" 로캘을 사용 하 여 스레드 A 시작에서 C 런타임 라이브러리 함수에만 합니다. 주 스레드 및 스레드 B에서 C 런타임 라이브러리 함수는 "C" 로캘에서 사용 하 여 계속 합니다. 그러나 이후에 [locale:: global](../standard-library/locale-class.md#global) 메서드는 "전역"은 로컬 변경, 모든 스레드에서 모든 c + + 표준 라이브러리 개체 "프랑스" 로캘을 사용 하 여 시작 합니다.  
  
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
  
```Output  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "French_France.1252"  
[Thread A] locale::global is set to "French_France.1252"  
  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "C"  
[Thread B] locale::global is set to "French_France.1252"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "C"  
[Thread main] locale::global is set to "French_France.1252"  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 주 스레드는 두 개의 하위 스레드를 생성 합니다. 첫 번째 스레드가 스레드 A 스레드별 로캘 호출 하 여 사용 하도록 설정 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`합니다. 두 번째 스레드가, 스레드 B 뿐 아니라 주 스레드 로컬을 사용 하지 마십시오. 그런 다음 B 스레드에서 사용 하 여 로캘을 변경할 수는 [setlocale](../preprocessor/setlocale.md) C 런타임 라이브러리의 기능입니다.  
  
 스레드 B 스레드 단위 로캘을 사용할 수 없으므로 주 스레드 및 스레드 B에서 C 런타임 라이브러리 함수는 "프랑스" 로캘을 사용 하 여 시작 합니다. C 런타임 라이브러리 스레드 A는 스레드 단위 로캘을 사용 하기 때문에 "C" 로캘에서 사용 하는 스레드 계속 작동 합니다. 또한 [setlocale](../preprocessor/setlocale.md) 개체는 계속 "C" 로캘에서 사용 하는 모든 c + + 표준 라이브러리는 c + + 표준 라이브러리 로캘의 영향을 주지 않습니다.  
  
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
  
```Output  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "French_France.1252"  
[Thread B] locale::global is set to "C"  
  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "C"  
[Thread A] locale::global is set to "C"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "French_France.1252"  
[Thread main] locale::global is set to "C"  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 주 스레드는 두 개의 하위 스레드를 생성 합니다. 첫 번째 스레드가 스레드 A 스레드별 로캘 호출 하 여 사용 하도록 설정 `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`합니다. 두 번째 스레드가, 스레드 B 뿐 아니라 주 스레드 로컬을 사용 하지 마십시오. 그런 다음 B 스레드에서 사용 하 여 로캘을 변경할 수는 [locale:: global](../standard-library/locale-class.md#global) c + + 표준 라이브러리의 메서드.  
  
 스레드 B 스레드 단위 로캘을 사용할 수 없으므로 주 스레드 및 스레드 B에서 C 런타임 라이브러리 함수는 "프랑스" 로캘을 사용 하 여 시작 합니다. C 런타임 라이브러리 스레드 A는 스레드 단위 로캘을 사용 하기 때문에 "C" 로캘에서 사용 하는 스레드 계속 작동 합니다. 그러나 이후에 [locale:: global](../standard-library/locale-class.md#global) 메서드는 "전역"은 로컬 변경, 모든 스레드에서 모든 c + + 표준 라이브러리 개체 "프랑스" 로캘을 사용 하 여 시작 합니다.  
  
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
  
```Output  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "French_France.1252"  
[Thread B] locale::global is set to "French_France.1252"  
  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "C"  
[Thread A] locale::global is set to "French_France.1252"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "French_France.1252"  
[Thread main] locale::global is set to "French_France.1252"  
```  
  
## <a name="see-also"></a>참고 항목  
 [이전 코드 (Visual c + +)를 위한 다중 스레딩 지원](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [국제화](../c-runtime-library/internationalization.md)   
 [로캘](../c-runtime-library/locale.md)   
 [\<clocale >](../standard-library/clocale.md)   
 [\<locale>](../standard-library/locale.md)   
 [locale 클래스](../standard-library/locale-class.md)