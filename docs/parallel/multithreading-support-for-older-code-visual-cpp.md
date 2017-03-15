---
title: "이전 코드를 위한 다중 스레드 지원(Visual C++) | Microsoft Docs"
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
  - "동시 실행 프로그래밍[C++]"
  - "여러 동시 실행 스레드"
  - "여러 스레드"
  - "다중 스레딩[C++]"
  - "다중 스레딩[C++], 다중 스레딩 정보"
  - "프로그래밍[C++], 다중 스레드"
  - "스레딩[C++]"
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 이전 코드를 위한 다중 스레드 지원(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 여러 실행 스레드를 동시에 실행할 수 있습니다.  다중 스레딩 기능을 사용하면 백그라운드 작업을 분리시키고 동시 입력 스트림을 관리하고 사용자 인터페이스를 관리하는 등 많은 작업을 수행할 수 있습니다.  
  
## 단원 내용  
 [C 및 Wind32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)  
 Microsoft Windows에서 다중 스레드 응용 프로그램을 만드는 기능을 지원합니다.  
  
 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)  
 프로세스 및 스레드의 정의, 다중 스레딩에 대한 MFC 접근 방법에 대해 설명합니다.  
  
 [다중 스레딩 및 로캘](../parallel/multithreading-and-locales.md)  
 다중 스레드 응용 프로그램에서 C 런타임 라이브러리와 표준 C\+\+ 라이브러리의 로캘 기능을 모두 사용할 때 발생하는 문제에 대해 설명합니다.  
  
## 관련 단원  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 응용 프로그램 내의 실행 스레드를 나타냅니다.  
  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Win32의 동기화 개체에 일반적인 기능을 제공하는 순수 가상 클래스에 대해 설명합니다.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 하나 이상의 프로세스의 제한된 스레드가 한 리소스에 액세스하도록 허용하는 동기화 개체인 세마포를 나타냅니다.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 한 스레드가 한 리소스에 상호 배타적으로 액세스하도록 허용하는 동기화 개체인 뮤텍스를 나타냅니다.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 한 번에 한 스레드씩 코드 섹션이나 한 리소스에 액세스하도록 허용하는 임계 섹션을 나타냅니다.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 한 스레드가 다른 스레드에게 이벤트가 발생했음을 알리도록 허용하는 동기화 개체인 이벤트를 나타냅니다.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 다중 스레드 프로그램에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 다중 스레드 프로그렘에서 한 리소스에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](http://msdn.microsoft.com/ko-kr/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Visual C\+\+ 라이브러리에 대한 개념적인 정보를 설명하는 항목 및 다양한 코딩 기술 및 기법을 설명하는 항목에 대한 링크를 제공합니다.