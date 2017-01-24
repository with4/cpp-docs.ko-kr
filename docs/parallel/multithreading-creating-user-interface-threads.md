---
title: "다중 스레딩: 사용자 인터페이스 스레드 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
  - "SECURITY_ATTRIBUTES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "다중 스레딩[C++], 사용자 인터페이스 스레드"
  - "스레딩[C++], 스레드 만들기"
  - "스레딩[C++], 사용자 인터페이스 스레드"
  - "스레딩[MFC], 사용자 인터페이스 스레드"
  - "사용자 인터페이스 스레드[C++]"
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다중 스레딩: 사용자 인터페이스 스레드 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 인터페이스 스레드는 일반적으로 응용 프로그램의 다른 부분을 실행하는 스레드와 별개로 사용자 입력을 처리하고 사용자 이벤트에 응답하는 데 사용됩니다.  주 응용 프로그램 스레드\(`CWinApp` 파생 클래스에서 제공\)가 이미 만들어져서 시작됩니다.  이 항목에서는 추가 사용자 인터페이스 스레드를 만드는 데 필요한 단계에 대해 설명합니다.  
  
 사용자 인터페이스 스레드를 만드는 경우 제일 먼저 [CWinThread](../mfc/reference/cwinthread-class.md)에서 클래스를 파생시켜야 합니다.  [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) 및 [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md) 매크로를 사용하여 이 클래스를 선언하고 구현해야 합니다.  이 클래스는 일부 함수를 재정의해야 하고 다른 함수를 재정의할 수도 있습니다.  다음 표에서는 함수 및 해당 함수의 용도에 대해 설명합니다.  
  
### 사용자 인터페이스 스레드를 만들 때 재정의할 함수  
  
|Function|용도|  
|--------------|--------|  
|[ExitInstance](../Topic/CWinThread::ExitInstance.md)|스레드가 종료되면 정리 작업을 수행하며  일반적으로 재정의됩니다.|  
|[InitInstance](../Topic/CWinThread::InitInstance.md)|스레드 인스턴스 초기화를 수행하며  재정의해야 합니다.|  
|[OnIdle](../Topic/CWinThread::OnIdle.md)|스레드별 유휴 시간 처리를 수행하며  일반적으로 재정의되지 않습니다.|  
|[PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|메시지를 **TranslateMessage**와 **DispatchMessage**에 디스패치하기 전에 필터링하며  일반적으로 재정의되지 않습니다.|  
|[ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|스레드의 메시지와 명령 처리기에서 throw된 처리되지 않는 예외를 가로채며  일반적으로 재정의되지 않습니다.|  
|[실행](../Topic/CWinThread::Run.md)|스레드에 대한 제어 함수이며  메시지 펌프를 포함합니다.  대부분 재정의되지 않습니다.|  
  
 MFC는 매개 변수 오버로딩을 통해 `AfxBeginThread` 의 두가지 버전을 제공합니다. 하나는 작업자 스레드만 만들 수 있고, 다른 하나는 사용자 인터페이스 스레드와 작업자 스레드를 모두 만들 수 있습니다.  사용자 인터페이스 스레드를 시작하려면 다음과 같은 정보를 제공하여 [AfxBeginThread](../Topic/AfxBeginThread.md)를 호출합니다.  
  
-   `CWinThread`에서 파생한 클래스의 [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)  
  
-   \(선택적 요소\) 원하는 우선 순위 수준.  기본값은 보통 우선 순위입니다.  사용할 수 있는 우선 순위 수준에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)를 참조하십시오.  
  
-   \(선택적 요소\) 스레드의 원하는 스택 크기.  기본값은 만드는 스레드와 스택의 크기가 동일합니다.  
  
-   \(선택적 요소\) 일시 중단된 상태에서 스레드가 만들어지기를 원하는 경우 **CREATE\_SUSPENDED**.  기본값은 0이며, 0이 아니면 스레드가 정상적으로 시작됩니다.  
  
-   \(선택적 요소\) 원하는 보안 특성.  기본값은 부모 스레드와 동일한 액세스입니다.  보안 정보 형식에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)를 참조하십시오.  
  
 `AfxBeginThread`는 사용자 대신 대부분의 작업을 수행합니다.  클래스의 새 개체를 만들고 사용자가 제공한 정보로 개체를 초기화하며 [CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md)를 호출하여 스레드를 실행합니다.  작성의 일부가 실패한 경우 전체 프로시저에서 모든 개체가 제대로 할당 해제되었는지 확인합니다.  
  
## 추가 정보  
  
-   [다중 스레딩: 스레드 종료](../parallel/multithreading-terminating-threads.md)  
  
-   [다중 스레딩: 작업자 스레드 만들기](../parallel/multithreading-creating-worker-threads.md)  
  
-   [\<caps:sentence id\="tgt49" sentenceid\="d446961ca833a037f83b141ec4859428" class\="tgtSentence"\>프로세스와 스레드\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## 참고 항목  
 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)