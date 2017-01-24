---
title: "스레드 컨트롤을 위한 C 런타임 라이브러리 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_beginthread 함수"
  - "_beginthreadex 함수"
  - "_endthread 함수"
  - "_endthreadex 함수"
  - "다중 스레딩[C++], 스레드 제어"
  - "스레딩[C++], 스레드 제어"
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 스레드 컨트롤을 위한 C 런타임 라이브러리 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 Win32 프로그램에는 최소한 하나 이상의 스레드가 있으며  모든 스레드는 추가 스레드를 만들 수 있습니다.  스레드는 작업을 신속하게 완료한 다음 종료되거나 프로그램의 유효 기간 동안 활성 상태를 유지할 수 있습니다.  
  
 LIBCMT 및 MSVCRT C 런타임 라이브러리는 스레드를 만들고 종료하기 위해 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) 및 [\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md) 함수를 제공합니다.  
  
 `_beginthread`와 `_beginthreadex` 함수는 새 스레드를 만들고 작업이 성공하면 스레드 식별자를 반환합니다.  스레드는 실행을 완료하면 자동으로 종료되거나 `_endthread` 또는 `_endthreadex`를 호출하여 스스로 종료할 수 있습니다.  
  
> [!NOTE]
>  Libcmt.lib로 빌드한 프로그램에서 C 런타임 루틴을 호출하려면 `_beginthread` 또는 `_beginthreadex` 함수를 사용하여 스레드를 시작해야 합니다.  Win32 함수 `ExitThread`와 `CreateThread`는 사용하지 마십시오.  일시 중단된 스레드가 C 런타임 데이터 구조에 대한 액세스를 완료할 때까지 둘 이상의 스레드가 대기 상태로 차단되어 있는 경우 `SuspendThread`를 사용하면 교착 상태가 발생할 수 있습니다.  
  
##  <a name="_core_the__beginthread_function"></a> \_beginthread 및 \_beginthreadex 함수  
 `_beginthread`와 `_beginthreadex` 함수는 새 스레드를 만듭니다.  스레드는 코드 및 데이터 세그먼트를 한 프로세스의 다른 스레드와 공유하지만 고유한 레지스터 값, 스택 공간 및 현재 명령 주소를 가집니다.  시스템은 각 스레드에 CPU 시간을 제공하므로 프로세스의 모든 스레드가 동시에 실행될 수 있습니다.  
  
 `_beginthread`와 `_beginthreadex`는 Win32 API의 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 함수와 유사하지만 다음과 같은 차이점이 있습니다.  
  
-   이러한 함수는 특정한 C 런타임 라이브러리 변수를 초기화합니다.  이것은 스레드에 C 런타임 라이브러리를 사용하는 경우에만 의미가 있습니다.  
  
-   `CreateThread`는 보안 특성을 제어합니다.  이 함수를 사용하여 일시 중단된 상태에서 스레드를 시작할 수 있습니다.  
  
 `_beginthread`와 `_beginthreadex`는 성공적으로 수행되면 새 스레드를 가리키는 핸들을 반환하고 오류가 있는 경우에는 오류 코드를 반환합니다.  
  
##  <a name="_core_the__endthread_function"></a> \_endthread 및 \_endthreadex 함수  
 [\_endthread](../c-runtime-library/reference/endthread-endthreadex.md) 함수는 `_beginthread`에서 만든 스레드를 종료하고, 이와 마찬가지로 `_endthreadex` 함수는 `_beginthreadex`에서 만든 스레드를 종료합니다.  스레드는 작업이 끝나면 자동으로 종료됩니다.  `_endthread`와 `_endthreadex`는 스레드 내에서 조건 종료에 유용합니다.  예를 들어, 통신 포트를 제어할 수 없게 되면 통신 처리 전용 스레드를 종료할 수 있습니다.  
  
## 참고 항목  
 [C 및 Wind32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)