---
title: "다중 스레딩: 동기화 클래스 사용 방법 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], multithreading
- threading [MFC], synchronization classes
- resources [C++], multithreading
- thread-safe classes [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], thread-safe class design
- threading [C++], synchronization
- multithreading [C++], synchronization classes
- threading [C++], thread-safe class design
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d85ea58588ea889fc8294b23604d47aef725135
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-how-to-use-the-synchronization-classes"></a>다중 스레딩: 동기화 클래스 사용 방법
스레드 간에 리소스 액세스를 동기화는 다중 스레드 응용 프로그램 작성 시에 일반적인 문제입니다. 두 개 이상의 있는 스레드에서 동시에 액세스 동일한 데이터 바람직하지 않은 및 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 스레드를 하나씩 업데이트할 수 있습니다는 구조체의 내용을 다른 스레드가 동일한 구조체의 내용을 읽는 동안 합니다. 알 수 없기 데이터 읽기는 스레드가: 이전 데이터를 새로 작성된 된 데이터 또는 둘 모두 합니다. MFC는 다양 한 동기화 및이 문제를 해결 하기 위해에 동기화 액세스 클래스를 제공 합니다. 이 클래스를 사용할 수 및 일반적인 다중 스레드 응용 프로그램 스레드로부터 안전한 클래스를 만드는 데 사용할 하는 방법을 설명 합니다.  
  
 일반적인 다중 스레드 응용 프로그램에 스레드 간에 공유 되는 리소스를 나타내는 클래스입니다. 제대로 설계 되 고 완전 한 스레드 안전 클래스 하지 않아도 되는 동기화 함수를 호출할 수 있습니다. 모든 것은 손상 얻을 수 있습니다 어떻게 대해서는 알아보지 클래스 사용에 가장 적합 하는 방법에 집중할 수 있도록 클래스에 내부적으로 처리 됩니다. 완전 한 스레드 안전 클래스를 만들어 효율적인 방법은 리소스 클래스에는 동기화 클래스를 병합 하는 것입니다. 동기화 클래스 공유 클래스에 병합 간단한 프로세스입니다.  
  
 예를 들어, 연결 된 계정 목록을 유지 관리 하는 응용 프로그램을 수행 합니다. 이 응용 프로그램은 최대 3 개의 계정을 사용 하 여 별도 창에서 검사할 수 있지만 특정 시간에 하나만 업데이트할 수 있습니다. 계정을 업데이트 될 때 업데이트 된 데이터는 데이터 보관 파일에 네트워크를 통해 전송 됩니다.  
  
 이 예제 응용 프로그램에는 세 가지 유형의 동기화 클래스를 모두 사용합니다. 사용 하 여 최대 3 개의 계정을 한 번에 검사할 수 수 있기 때문에 [CSemaphore](../mfc/reference/csemaphore-class.md) 3 개의 뷰 개체에 대 한 액세스를 제한할 수 있습니다. 확인 하려고 할 때 네 번째 계정 발생 하면 응용 프로그램 처음 3 개 창 중 하나를 닫습니다 하거나 실패할 때까지 기다리거나 합니다. 응용 프로그램에 사용 하 여 계정을 업데이트 되 면 [아니오](../mfc/reference/ccriticalsection-class.md) 계정 하나에 한 번에 업데이트 됩니다. 업데이트가 성공 하면 신호를 보내고 [CEvent](../mfc/reference/cevent-class.md), 이벤트 신호를 기다리는 스레드를 해제 합니다. 이 스레드는 데이터 보관을 새 데이터를 보냅니다.  
  
##  <a name="_mfc_designing_a_thread.2d.safe_class"></a>스레드 안전 클래스 디자인  
 완전 한 스레드 안전 클래스를 확인, 먼저에 적절 한 동기화 클래스를 추가 공유 클래스를 데이터 멤버로 합니다. 이전 계정 관리 예제에서는 **CSemaphore** 데이터 멤버는 뷰 클래스에 추가 됩니다 한 `CCriticalSection` 데이터 멤버는 연결 리스트 클래스에 추가 됩니다 및 `CEvent` 데이터 멤버는 데이터에 추가 됩니다 저장소 클래스입니다.  
  
 클래스의 데이터를 수정 하거나 제어 된 리소스에 액세스 하는 모든 멤버 함수에 대 한 동기화 호출 다음에 추가 합니다. 각 함수에서 만들어야 중 하나는 [경우 CSingleLock](../mfc/reference/csinglelock-class.md) 또는 [CMultiLock](../mfc/reference/cmultilock-class.md) 개체와 해당 개체의 호출 `Lock` 함수입니다. 개체의 소멸자가 호출 하는 잠금 개체 범위를 벗어나면 소멸 될 때 `Unlock` , 리소스를 해제 합니다. 호출할 수는 물론, `Unlock` 직접 들어 있습니다.  
  
 이러한 방식으로 스레드 안전 클래스 디자인는 다중 스레드 응용 프로그램으로 쉽게 스레드로부터 안전 하지 않은 클래스 하지만 더 높은 수준의 보안에서 사용할 수 있습니다. 리소스의 클래스에는 동기화 개체 및 동기화 액세스 개체를 캡슐화 동기화 코드를 유지 관리 작업의 단점은 없이 완전 한 스레드 안전 프로그래밍의 모든 이점을 제공 합니다.  
  
 다음 코드 예제에서는 데이터 멤버를 사용 하 여이 메서드를 보여 줍니다. `m_CritSection` (형식의 `CCriticalSection`) 공유 리소스 클래스에서 선언 된 및 `CSingleLock` 개체입니다. 공유 리소스의 동기화 (에서 파생 된 `CWinThread`)를 만들어 시도 `CSingleLock` 개체의 주소를 사용 하 여는 `m_CritSection` 개체입니다. 리소스를 잠글 하려고 시도 하 고을 가져올 때 작업 공유 개체에 대. 리소스를 호출 하 여 잠금 해제 되어 작업이 완료 되 면 `Unlock`합니다.  
  
```  
CSingleLock singleLock(&m_CritSection);  
singleLock.Lock();  
// resource locked  
//.usage of shared resource...  
  
singleLock.Unlock();  
```  
  
> [!NOTE]
>  `CCriticalSection`를 다른 MFC 동기화 클래스와 달리 없는 시간이 지정 된 잠금 요청 수입니다. 스레드 수 있게를 대기 기간에는 제한이 없습니다.  
  
 이 방법의 단점은 동기화 개체가 추가 하지 않고 클래스는 동일한 클래스 보다 조금 느리기 될 됩니다. 또한 둘 이상의 스레드 개체를 삭제할 수 없으면 병합된 방법이 수 되지 경우가 있습니다. 이 경우 별도 동기화 개체를 유지 관리 하는 것이 좋습니다.  
  
 동기화 클래스 여러 상황에서 사용할를 결정 하는 방법에 대 한 정보를 참조 하십시오. [다중 스레딩: 동기화 클래스를 사용 하는 경우](../parallel/multithreading-when-to-use-the-synchronization-classes.md)합니다. 동기화에 대 한 자세한 내용은 참조 [동기화](http://msdn.microsoft.com/library/windows/desktop/ms686353) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다. MFC의 다중 스레딩을 지원에 대 한 자세한 내용은 참조 [c + + 및 MFC 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)