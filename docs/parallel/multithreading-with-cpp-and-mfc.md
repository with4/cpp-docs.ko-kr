---
title: "C++ 및 MFC에서 다중 스레딩 | Microsoft Docs"
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
  - "CWinThread 클래스, 용도"
  - "MFC[C++], 다중 스레딩"
  - "다중 스레딩[C++], MFC"
  - "동기화[C++], 다중 스레딩"
  - "동기화 클래스[C++]"
  - "스레딩[C++], MFC"
  - "스레딩[MFC]"
  - "스레딩[MFC], 스레딩 정보"
  - "사용자 인터페이스 스레드[C++]"
  - "작업자 스레드[C++]"
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 및 MFC에서 다중 스레딩
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC\(Microsoft Foundation Class\) 라이브러리는 다중 스레드 응용 프로그램을 지원합니다.  이 항목에서는 프로세스와 스레드에 대해 설명하고 다중 스레딩에 대한 MFC의 접근 방식에 대해 설명합니다.  
  
 프로세스는 응용 프로그램의 실행 인스턴스입니다.  예를 들어, 메모장 아이콘을 두 번 클릭하면 메모장을 실행하는 프로세스를 시작하게 됩니다.  
  
 스레드는 한 프로세스 내의 실행 경로입니다.  메모장을 시작하면 운영 체제는 프로세스를 만들고 해당 프로세스의 주 스레드를 실행합니다.  이 스레드가 종료되면 프로세스도 종료됩니다.  주 스레드는 시작 코드에서 함수 주소의 형식으로 운영 체제에 제공됩니다.  일반적으로 제공된 **main** 함수 또는 `WinMain` 함수의 주소입니다.  
  
 원하는 경우 응용 프로그램에 추가 스레드를 만들 수 있습니다.  백그라운드 작업이나 유지 관리 작업이 완료될 때까지 기다리지 않도록 추가 스레드에서 이러한 작업을 처리하게 할 수 있습니다.  MFC 응용 프로그램의 모든 스레드는 [CWinThread](../mfc/reference/cwinthread-class.md) 개체에 의해 나타납니다.  대부분의 경우 이러한 개체를 명시적으로 만들 필요가 없으며 대신 [AfxBeginThread](../Topic/AfxBeginThread.md) 프레임워크 도우미 함수를 호출하면 `CWinThread` 개체가 만들어집니다.  
  
 MFC는 사용자 인터페이스 스레드와 작업자 스레드라는 두 가지 유형의 스레드를 구분합니다.  사용자 인터페이스 스레드는 일반적으로 사용자 입력을 처리하고 사용자가 생성한 이벤트와 메시지에 응답하는 데 사용되며,  작업자 스레드는 사용자가 입력하지 않아도 되는 작업\(예: 다시 계산\)을 완료하는 데 사용됩니다.  Win32 API는 두 가지 스레드 유형을 구분하지 않으며 스레드를 실행할 수 있도록 스레드의 시작 주소만 알면 됩니다.  MFC에서는 사용자 인터페이스에 이벤트에 메시지 펌프를 제공하여 사용자 인터페이스 스레드를 특별하게 처리합니다.  `CWinApp`는 `CWinThread`에서 파생되고 사용자가 생성한 이벤트와 메시지를 처리하므로 사용자 인터페이스 스레드 개체의 한 예라고 할 수 있습니다.  
  
 두 개 이상의 스레드가 동일한 개체에 액세스해야 하는 경우에는 특별히 주의해야 합니다.  [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md)에서는 이러한 상황에서 발생할 수 있는 문제를 해결할 때 사용할 수 있는 기법을 설명합니다.  [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md)에서는 단일 개체에 대한 여러 스레드의 액세스를 동기화하는 데 사용할 수 있는 클래스의 사용 방법에 대해 설명합니다.  
  
 한 번에 두 개 이상의 스레드가 개체에 액세스하지 않도록 해야 하므로 다중 스레드 프로그래밍 작성 및 디버깅은 복잡하고 힘든 작업입니다.  다중 스레딩 항목에서는 다중 스레드 프로그래밍의 기본 사항은 제외하고 다중 스레드 프로그램에서 MFC를 사용하는 방법에 대해서만 설명합니다.  Visual C\+\+에 포함된 다중 스레드 MFC 샘플은 MFC에 포함되지 않은 일부 다중 스레드 기능 추가 및 Win32 API에 대한 기본적인 내용만 소개합니다.  
  
 운영 체제에서 프로세스와 스레드가 처리되는 방식에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Processes and Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841)를 참조하십시오.  
  
 MFC 다중 스레딩 지원에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [다중 스레딩: 사용자 인터페이스 스레드 만들기](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [다중 스레딩: 작업자 스레드 만들기](../parallel/multithreading-creating-worker-threads.md)  
  
-   [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [다중 스레딩: 스레드 종료](../parallel/multithreading-terminating-threads.md)  
  
-   [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md)  
  
-   [다중 스레딩: 동기화 클래스 사용 시기](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## 참고 항목  
 [이전 코드를 위한 다중 스레드 지원\(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)