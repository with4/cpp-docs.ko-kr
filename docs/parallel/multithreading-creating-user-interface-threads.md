---
title: "다중 스레딩: 사용자 인터페이스 스레드 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 105685e0db4689978ef1e6f8615bb5e5f8acdd43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-creating-user-interface-threads"></a>다중 스레딩: 사용자 인터페이스 스레드 만들기
사용자 인터페이스 스레드는 대개 응용 프로그램의 다른 부분을 실행 하는 스레드 독립적으로 사용자 이벤트에 응답 하 고 사용자 입력을 처리 합니다. 기본 응용 프로그램 스레드 (에 제공 된 프로그램 `CWinApp`-파생 클래스)가 이미 만들어져서 시작 됩니다. 이 항목에서는 추가 사용자 인터페이스 스레드를 만드는 데 필요한 단계에 설명 합니다.  
  
 가장 먼저 해야 할 사용자 인터페이스 스레드를 만드는 경우는에서 클래스를 파생 [CWinThread](../mfc/reference/cwinthread-class.md)합니다. 선언 하 고이 구현 해야 클래스를 사용 하는 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) 및 [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) 매크로입니다. 이 클래스는 일부 함수를 재정의 해야 하며 다른 사용자를 재정의할 수 있습니다. 이러한 함수 및 수행 해야 할 작업은 다음 표에 표시 됩니다.  
  
### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>사용자 인터페이스 스레드를 만들 때 재정의할 함수  
  
|함수|용도|  
|--------------|-------------|  

|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)| 스레드가 종료 되 면 정리를 수행 합니다. 일반적으로 재정의 합니다. |  
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)| 스레드 인스턴스 초기화를 수행 합니다. 재정의 해야 합니다. |  
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)| 스레드 관련 유휴 시간 처리를 수행 합니다. 재정의 하지 않는. |  
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)| 디스패치 되기 전에 메시지를 필터링 **TranslateMessage** 및 **DispatchMessage**합니다. 재정의 하지 않는. |  
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)| 스레드의 메시지 및 명령 처리기에서 throw 된 처리 되지 않은 예외를 차단 합니다. 재정의 하지 않는. |  
|[실행](../mfc/reference/cwinthread-class.md#run)| 스레드에 대 한 함수를 제어합니다. 메시지 펌프를 포함합니다. 재정의 된 경우는 거의 없습니다. |  

  
 MFC는 매개 변수 오버로드를 통해 `AfxBeginThread`의 두 가지 버전을 제공합니다. 하나는 작업자 스레드만 만들 수 있고, 다른 하나는 사용자 인터페이스 스레드 또는 작업자 스레드를 만들 수 있습니다. 사용자 인터페이스 스레드를 시작 하려면의 두 번째 오버 로드를 호출 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 다음 정보를 제공 합니다.  
  
-   [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 에서 파생 된 클래스의 `CWinThread`합니다.  
  
-   (선택 사항) 원하는 우선 순위 수준입니다. 기본값은 보통 우선 순위입니다. 사용 가능한 우선 순위 수준에 대 한 자세한 내용은 참조 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
-   (선택 사항) 스레드에 대 한 원하는 스택 크기입니다. 기본값은 만드는 스레드와 같은 크기 스택.  
  
-   (선택 사항) **CREATE_SUSPENDED** 스레드 일시 중단 된 상태로 만들 수를 선택 합니다. 기본값은 0으로, 또는 스레드를 정상적으로 시작 합니다.  
  
-   (선택 사항) 원하는 보안 특성입니다. 기본값은 부모 스레드는 동일한 액세스 권한을 부여 합니다. 이 보안 정보는 형식에 대 한 자세한 내용은 참조 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
 `AfxBeginThread`대부분의 작업을 수행 합니다. 클래스의 새 개체를 만들고, 사용자가 제공한 정보 및 호출으로 초기화 [CWinThread::CreateThread](../mfc/reference/cwinthread-class.md#createthread) 스레드 실행을 시작 합니다. 모든 개체가 제대로 할당 해제 생성 부분이 실패 해야 되도록 전체 프로시저에서 검사가 수행 됩니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [다중 스레딩: 스레드 종료](../parallel/multithreading-terminating-threads.md)  
  
-   [다중 스레딩: 작업자 스레드 만들기](../parallel/multithreading-creating-worker-threads.md)  
  
-   [프로세스 및 스레드](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)