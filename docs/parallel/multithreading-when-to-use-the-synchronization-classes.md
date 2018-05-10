---
title: '다중 스레딩: 동기화 클래스를 사용 하는 경우 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b05922b826de81b5192b183e1c0afdfcda189f03
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-when-to-use-the-synchronization-classes"></a>다중 스레딩: 동기화 클래스 사용 시기
MFC와 함께 제공 되는 다중 스레드 클래스 두 범주로 나누어집니다: 동기화 개체 ([CSyncObject](../mfc/reference/csyncobject-class.md), [CSemaphore](../mfc/reference/csemaphore-class.md), [CMutex](../mfc/reference/cmutex-class.md), [ 아니오](../mfc/reference/ccriticalsection-class.md), 및 [CEvent](../mfc/reference/cevent-class.md)) 및 동기화 개체에 액세스 ([CMultiLock](../mfc/reference/cmultilock-class.md) 및 [경우 CSingleLock](../mfc/reference/csinglelock-class.md)).  
  
 동기화 클래스 리소스의 무결성을 보장 리소스에 대 한 액세스를 제어 해야 하는 경우에 사용 됩니다. 동기화 액세스 클래스는 이러한 리소스에 액세스 하는 데 사용 됩니다. 이 항목에서는 각 클래스를 사용 하는 경우.  
  
 동기화 클래스 사용 해야를 확인 하려면 다음과 같은 일련의 질문을 요청 합니다.  
  
1.  응용 프로그램 특정 작업이 실행 되는 리소스에 액세스 하기 전에 대기 하는 (예를 들어 데이터를 수신한 통신 포트에서 파일에 쓸 수 있습니다)?  
  
     예 인 경우 사용 `CEvent`합니다.  
  
2.  수 이상의 스레드가 동일한 응용 프로그램 액세스 내에서이 리소스 한 번에 (예를 들어 응용 프로그램 허용 최대 5 개 창에서 같은 문서에 뷰 사용)?  
  
     예 인 경우 사용 `CSemaphore`합니다.  
  
3.  이 리소스를 사용 하 여 둘 이상의 응용 프로그램 수 있습니다 (예를 들어 리소스는 DLL)?  
  
     예 인 경우 사용 `CMutex`합니다.  
  
     그렇지 않은 경우, 사용 하 여 `CCriticalSection`합니다.  
  
 **CSyncObject** 직접 사용 되지 않습니다. 다른 4 개의 동기화 클래스에 대 한 기본 클래스입니다.  
  
## <a name="example-1-using-three-synchronization-classes"></a>예제 1: 3 개의 동기화 클래스 사용  
 예를 들어, 연결 된 계정 목록을 유지 관리 하는 응용 프로그램을 수행 합니다. 이 응용 프로그램은 최대 3 개의 계정을 사용 하 여 별도 창에서 검사할 수 있지만 특정 시간에 하나만 업데이트할 수 있습니다. 계정을 업데이트 될 때 업데이트 된 데이터는 데이터 보관 파일에 네트워크를 통해 전송 됩니다.  
  
 이 예제 응용 프로그램에는 세 가지 유형의 동기화 클래스를 모두 사용합니다. 사용 하 여 최대 3 개의 계정을 한 번에 검사할 수 수 있기 때문에 `CSemaphore` 3 개의 뷰 개체에 대 한 액세스를 제한할 수 있습니다. 확인 하려고 할 때 네 번째 계정 발생 하면 응용 프로그램 처음 3 개 창 중 하나를 닫습니다 하거나 실패할 때까지 기다리거나 합니다. 응용 프로그램에 사용 하 여 계정을 업데이트 되 면 `CCriticalSection` 계정 하나에 한 번에 업데이트 됩니다. 업데이트가 성공 하면 신호를 보내고 `CEvent`, 이벤트 신호를 기다리는 스레드를 해제 합니다. 이 스레드는 데이터 보관을 새 데이터를 보냅니다.  
  
## <a name="example-2-using-synchronization-access-classes"></a>예제 2: 동기화 액세스 클래스를 사용 하 여  
 선택 동기화 액세스 클래스를 사용 하 여은 훨씬 더 간단 합니다. 응용 프로그램 관련 제어 된 단일 리소스에만 액세스를 사용 하 여 `CSingleLock`합니다. 사용 하 여 다양 한 제어 된 리소스 중 하나에 대 한 액세스를 해야 하는 경우 `CMultiLock`합니다. 예 1, `CSingleLock` 대체, 각각의 경우에 자원이 하나만 특정 시간에 필요 하므로.  
  
 동기화 클래스 사용 방법에 대 한 정보를 참조 하십시오. [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다. 동기화에 대 한 정보를 참조 하십시오. [동기화](http://msdn.microsoft.com/library/windows/desktop/ms686353) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다. MFC의 다중 스레딩을 지원에 대 한 정보를 참조 하십시오. [c + + 및 MFC 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)