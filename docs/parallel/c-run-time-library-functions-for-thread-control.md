---
title: 스레드 제어에 대 한 C 런타임 라이브러리 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- _endthread function
- threading [C++], controlling threads
- multithreading [C++], controlling threads
- _beginthreadex function
- _endthreadex function
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a505bae156edba6798812b807d7ab5c6ea9e396
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="c-run-time-library-functions-for-thread-control"></a>스레드 컨트롤을 위한 C 런타임 라이브러리 함수
모든 Win32 프로그램에 하나 이상의 스레드가 있어야 합니다. 모든 스레드가 추가 스레드를 만들 수 있습니다. 스레드 수 신속 하 게 작업을 완료 한 다음 종료 또는 프로그램의 수명 동안 비활성 상태로 유지 될 수 있는 합니다.  
  
 스레드 생성 및 종료에 대 한 다음과 같은 기능을 제공 하는 LIBCMT 및 MSVCRT C 런타임 라이브러리: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) 및 [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)합니다.  
  
 `_beginthread` 및 `_beginthreadex` 함수 새 스레드를 만들고 작업이 성공 하면 스레드 식별자를 반환 합니다. 스레드를 호출 하 여 스스로 종료할 수 있습니다 또는 실행을 완료 하면 자동으로 종료 `_endthread` 또는 `_endthreadex`합니다.  
  
> [!NOTE]
>  Libcmt.lib를 사용 하 여 빌드한 프로그램에서 C 런타임 루틴을 호출 하려는 경우 사용 하 여 스레드를 시작 해야는 `_beginthread` 또는 `_beginthreadex` 함수입니다. Win32 함수를 사용 하지 마십시오 `ExitThread` 및 `CreateThread`합니다. 사용 하 여 `SuspendThread` 일시 중단 된 스레드 C 런타임 데이터 구조에 대 한 액세스의 완료를 대기 중인 둘 이상의 스레드가 차단 하면 교착 상태가 발생할 수 있습니다.  
  
##  <a name="_core_the__beginthread_function"></a> _Beginthread 및 _beginthreadex 함수  
 `_beginthread` 및 `_beginthreadex` 새 스레드를 만들 함수입니다. 스레드는 프로세스의 코드와 데이터 세그먼트는 프로세스의 다른 스레드를 공유 하지만 고유한 고유한 레지스터 값, 스택 공간 및 현재 명령의 주소입니다. 시스템은 프로세스의 모든 스레드는 동시에 실행할 수 있도록 각 스레드를 CPU 시간을 제공 합니다.  
  
 `_beginthread` 및 `_beginthreadex` 는 비슷합니다는 [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Win32 api에서 함수 하지만 이러한 차이 포함 합니다.  
  
-   특정 C 런타임 라이브러리 변수 초기화 하 여 합니다. 사용자 스레드에 C 런타임 라이브러리를 사용 하는 경우에 유용 합니다.  
  
-   `CreateThread` 보안 특성을 제어를 합니다. 일시 중단된 된 상태에서 스레드를 시작 하려면이 함수를 사용할 수 있습니다.  
  
 `_beginthread` 및 `_beginthreadex` 오류가 발생 했습니다 경우 성공 하는 경우 새 스레드 또는 오류 코드에 대 한 핸들을 반환 합니다.  
  
##  <a name="_core_the__endthread_function"></a> _Endthread 및 _endthreadex 함수  
 [_endthread](../c-runtime-library/reference/endthread-endthreadex.md) 함수에서 만든 스레드를 종료 `_beginthread` (고 마찬가지로 `_endthreadex` 하 여 만든 스레드 `_beginthreadex`). 스레드 끝나면 자동으로 종료 합니다. `_endthread` 및 `_endthreadex` 스레드 내에서 조건부 종료 하는 데 유용 합니다. 예를 들어 전용된 스레드를 처리 하는 통신 통신 포트를 제어할 수 없는 경우 종료 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 및 Win32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)