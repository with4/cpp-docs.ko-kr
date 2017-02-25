---
title: "다중 스레딩: 동기화 클래스 사용 방법 | Microsoft Docs"
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
  - "MFC[C++], 다중 스레딩"
  - "다중 스레딩[C++], 동기화 클래스"
  - "리소스[C++], 다중 스레딩"
  - "동기화[C++], 다중 스레딩"
  - "동기화 클래스[C++]"
  - "스레딩[C++], 동기화"
  - "스레딩[C++], 스레드 안전 클래스 디자인"
  - "스레딩[MFC], 동기화 클래스"
  - "스레딩[MFC], 스레드 안전 클래스 디자인"
  - "스레드로부터 안전한 클래스[C++]"
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 다중 스레딩: 동기화 클래스 사용 방법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다중 스레드 응용 프로그램을 작성하는 경우 일반적으로 스레드 사이에 리소스 액세스를 동기화해야 하는 문제가 발생합니다.  두 개 이상의 스레드가 동일한 데이터에 동시에 액세스하면 원하지 않고 예측할 수 없는 결과를 초래할 수 있습니다.  예를 들어, 어떤 스레드에서 구조체의 내용을 읽고 있는 동안 또 다른 스레드에서 동일한 구조체의 내용을 업데이트할 수 있습니다.  이런 경우 읽기 작업을 수행하는 스레드가 어떤 데이터를 받는지 알 수 없습니다. 이전 데이터, 새로 작성된 데이터 또는 두 데이터가 혼합될 수도 있습니다.  MFC는 이 문제를 해결하기 위해 많은 동기화 클래스와 동기화 액세스 클래스를 제공합니다.  이 항목에서는 사용할 수 있는 클래스 및 일반적인 다중 스레드 응용 프로그램에서 이들 클래스를 사용하여 스레드 안전 클래스를 만드는 방법에 대해 설명합니다.  
  
 일반적인 다중 스레드 응용 프로그램에는 스레드 사이에 공유되는 리소스를 나타내는 클래스가 있습니다.  올바로 디자인된 완전한 스레드 안전 클래스라면 동기화 함수를 호출할 필요가 없습니다.  모든 작업이 클래스 내부에서 처리되므로 클래스가 손상될 수 있는 방법이 아니라 클래스를 최대한 활용할 수 있는 방법에만 주의하면 됩니다.  완전한 스레드 안전 클래스를 만드는 효율적인 방법은 동기화 클래스를 리소스 클래스에 병합하는 것입니다.  동기화 클래스를 공유 클래스에 병합하는 프로세스는 매우 간단합니다.  
  
 한 예로, 연결된 계정 리스트를 유지 관리하는 응용 프로그램을 가정해 볼 수 있습니다.  이 응용 프로그램은 별도의 창에서 최대 3개의 계정을 검사할 수 있지만 하나의 계정만 특정 시간에 업데이트할 수 있습니다.  계정이 업데이트되면 업데이트된 데이터는 네트워크를 통해 데이터 보관 저장소에 전달됩니다.  
  
 이 예제 응용 프로그램에서는 3가지 유형의 동기화 클래스를 모두 사용합니다.  동시에 최대 3개의 계정을 검사할 수 있으므로 [CSemaphore](../mfc/reference/csemaphore-class.md)를 사용하여 3개의 뷰 개체에 대한 액세스를 제한합니다.  넷째 계정을 보려고 하면 응용 프로그램은 처음 3개의 창 중 하나가 닫힐 때까지 기다리거나 작업이 실패합니다.  계정이 업데이트되면 응용 프로그램은 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)을 사용하여 한 번에 한 개의 계정만 업데이트되게 합니다.  업데이트가 성공하면 [CEvent](../mfc/reference/cevent-class.md)에 신호를 보내고 이 클래스는 이벤트에서 신호를 받을 때까지 기다리는 스레드를 해제합니다.  이 스레드는 새 데이터를 데이터 보관 저장소에 보냅니다.  
  
##  <a name="_mfc_designing_a_thread.2d.safe_class"></a> 스레드 안전 클래스 디자인  
 완전한 스레드 안전 클래스를 만들려면 먼저 적절한 동기화 클래스를 공유 클래스에 데이터 멤버로 추가합니다.  앞에서 설명한 계정 관리 예제에서 **CSemaphore** 데이터 멤버는 뷰 클래스에 추가되고 `CCriticalSection`데이터 멤버는 연결 리스트 클래스에 추가되며 `CEvent`데이터 멤버는 데이터 저장소 클래스에 추가됩니다.  
  
 그런 다음 클래스에서 데이터를 수정하거나 제어된 리소스에 액세스하는 모든 멤버 함수에 대해 동기화 호출을 추가합니다.  각 함수에서 [CSingleLock](../mfc/reference/csinglelock-class.md) 또는 [CMultiLock](../mfc/reference/cmultilock-class.md) 개체를 만들어서 이 개체의 `Lock` 함수를 호출해야 합니다.  잠금 개체가 범위에서 벗어나서 소멸하면 개체의 소멸자가 `Unlock`을 호출하여 리소스를 해제합니다.  물론 사용자가 직접 `Unlock`을 호출할 수도 있습니다.  
  
 이런 방식으로 스레드 안전 클래스를 디자인하면 다중 스레드 응용 프로그램에서 스레드 안전 방식이 아닌 클래스만큼 쉽게 사용하면서도 높은 수준의 안전성을 제공할 수 있습니다.  동기화 개체와 동기화 액세스 개체를 리소스의 클래스에 캡슐화하면 동기화 코드를 유지 관리해야 하는 단점 없이 완전한 스레드 안전 프로그래밍의 모든 이점을 활용할 수 있습니다.  
  
 다음 코드 예제에서는 공유 리소스 클래스와 `CSingleLock` 개체에 선언된 `CCriticalSection` 형식의 `m_CritSection` 데이터 멤버를 사용하여 이 방법에 대해 설명합니다.  `m_CritSection` 개체의 주소를 사용하여 `CSingleLock` 개체를 만드는 방법을 통해 `CWinThread`에서 파생된 공유 리소스의 동기화를 시도합니다.  리소스를 잠근 다음 획득하면 공유 개체에 대한 작업을 수행합니다.  작업이 완료되면 `Unlock`을 호출하여 리소스 잠금을 해제합니다.  
  
```  
CSingleLock singleLock(&m_CritSection);  
singleLock.Lock();  
// resource locked  
//.usage of shared resource...  
  
singleLock.Unlock();  
```  
  
> [!NOTE]
>  다른 MFC 동기화 클래스와 달리 `CCriticalSection`은 시간 제한 잠금 요청 옵션을 제공하지 않습니다.  스레드를 다시 사용할 수 있을 때까지 대기 시간에 제한이 없습니다.  
  
 이 방법의 단점은 동기화 개체가 추가되지 않은 동일한 클래스에 비해 속도가 다소 느리다는 것입니다.  또한 두 개 이상의 스레드에서 개체를 삭제할 수 있는 경우 병합 방법이 항상 올바르게 동작하지 않을 수도 있습니다.  이런 경우 별도의 동기화 개체를 유지하는 것이 좋습니다.  
  
 여러 상황에서 사용할 동기화 클래스를 결정하는 데 대한 내용은 [다중 스레딩: 동기화 클래스 사용 시기](../parallel/multithreading-when-to-use-the-synchronization-classes.md)를 참조하십시오.  동기화에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)을 참조하십시오.   MFC에서 다중 스레딩 지원에 대한 자세한 내용은 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)을 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)