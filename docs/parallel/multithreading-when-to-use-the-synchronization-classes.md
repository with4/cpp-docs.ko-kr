---
title: "다중 스레딩: 동기화 클래스 사용 시기 | Microsoft Docs"
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
  - "제어된 리소스 액세스[C++]"
  - "다중 스레딩[C++], 동기화 클래스"
  - "리소스[C++], 다중 스레딩"
  - "동기화[C++], 다중 스레딩"
  - "동기화 액세스 클래스[C++]"
  - "동기화 클래스[C++]"
  - "스레딩[C++], 동기화"
  - "스레딩[MFC], 동기화 클래스"
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 다중 스레딩: 동기화 클래스 사용 시기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC에 제공되는 6개의 다중 스레드 클래스는 동기화 개체\([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [CCriticalSection](../mfc/reference/ccriticalsection-class.md) 및 [CEvent](../mfc/reference/cevent-class.md)\)와 동기화 액세스 개체\([CMultiLock](../mfc/reference/cmultilock-class.md) 및 [CSingleLock](../mfc/reference/csinglelock-class.md)\)의 두 가지 범주로 분류됩니다.  
  
 동기화 클래스는 리소스의 무결성을 보장하기 위해 리소스에 대한 액세스를 제어해야 하는 경우 사용됩니다.  동기화 액세스 클래스는 제어된 리소스에 액세스하기 위해 사용됩니다.  이 항목에서는 각 클래스의 사용 시기에 대해 설명합니다.  
  
 어떤 동기화 클래스를 사용해야 하는지 결정하려면 다음과 같은 여러 가지 질문을 확인하십시오.  
  
1.  응용 프로그램이 리소스에 액세스하려면 어떤 이벤트가 발생할 때까지 기다려야 합니까? 예를 들어, 데이터를 파일에 쓰려면 먼저 통신 포트에서 데이터를 받아야 합니다.  
  
     이러한 경우 `CEvent`를 사용하십시오.  
  
2.  동일한 응용 프로그램에서 두 개 이상의 스레드가 동시에 이 리소스에 액세스합니까? 예를 들어, 응용 프로그램이 동일한 문서에 대해 뷰를 포함한 최대 5개의 창을 허용합니다.  
  
     이러한 경우 `CSemaphore`를 사용하십시오.  
  
3.  두 개 이상의 응용 프로그램에서 이 리소스를 사용할 수 있습니까? 예를 들어, 리소스가 DLL에 있습니다.  
  
     이러한 경우 `CMutex`를 사용하십시오.  
  
     그렇지 않은 경우 `CCriticalSection`을 사용하십시오.  
  
 **CSyncObject**는 직접 사용되지 않습니다.  이것은 다른 4개의 동기화 클래스에 대한 기본 클래스입니다.  
  
## 예제 1: 3개의 동기화 클래스 사용  
 한 예로, 연결된 계정 리스트를 유지 관리하는 응용 프로그램을 가정해 볼 수 있습니다.  이 응용 프로그램은 별도의 창에서 최대 3개의 계정을 검사할 수 있지만 하나의 계정만 특정 시간에 업데이트할 수 있습니다.  계정이 업데이트되면 업데이트된 데이터는 네트워크를 통해 데이터 보관 저장소에 전달됩니다.  
  
 이 예제 응용 프로그램에서는 3가지 유형의 동기화 클래스를 모두 사용합니다.  동시에 최대 3개의 계정을 검사할 수 있으므로 `CSemaphore`를 사용하여 3개의 뷰 개체에 대한 액세스를 제한합니다.  넷째 계정을 보려고 하면 응용 프로그램은 처음 3개의 창 중 하나가 닫힐 때까지 기다리거나 작업이 실패합니다.  계정이 업데이트되면 응용 프로그램은 `CCriticalSection`을 사용하여 한 번에 한 개의 계정만 업데이트되게 합니다.  업데이트가 성공하면 `CEvent`에 신호를 보내고 이 클래스는 이벤트에서 신호를 받을 때까지 기다리는 스레드를 해제합니다.  이 스레드는 새 데이터를 데이터 보관 저장소에 보냅니다.  
  
## 예제 2: 동기화 액세스 클래스 사용  
 사용할 동기화 액세스 클래스를 선택하는 것은 훨씬 간단합니다.  응용 프로그램에서 제어된 단일 리소스에만 액세스하면 되는 경우 `CSingleLock`을 사용합니다.  제어된 여러 리소스 중 어떤 하나에 액세스해야 하는 경우에는 `CMultiLock`을 사용합니다.  예제 1에서는 특정 시간에 한 개의 리소스만 필요하기 때문에 `CSingleLock`이 사용됩니다.  
  
 동기화 클래스를 사용하는 방법에 대한 자세한 내용은 [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md)을 참조하십시오.  동기화에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)을 참조하십시오.  MFC에서 다중 스레딩 지원에 대한 자세한 내용은 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)을 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)