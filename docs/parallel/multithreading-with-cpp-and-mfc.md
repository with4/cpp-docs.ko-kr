---
title: C + + 및 MFC를 사용한 다중 스레딩 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], multithreading
- threading [C++], MFC
- worker threads [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], about threading
- CWinThread class, purpose of
- multithreading [C++], MFC
- threading [MFC]
- user interface threads [C++]
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 778602a0e9236ad8cc788d8a2306e8f2d143ec49
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688572"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ 및 MFC에서 다중 스레딩
Microsoft Foundation 클래스 (MFC) 라이브러리는 다중 스레드 응용 프로그램에 대 한 지원을 제공합니다. 이 항목에서는 프로세스 및 스레드 및 MFC 접근 방식을 설명의 다중 스레딩과 합니다.  
  
 프로세스는 응용 프로그램의 실행 중인 인스턴스입니다. 예를 들어 메모장 아이콘을 두 번 클릭 하면 메모장을 실행 하는 프로세스를 시작 합니다.  
  
 스레드는 프로세스 내에서 실행 경로입니다. 메모장을 시작 하면 운영 체제는 프로세스를 생성 하 고 해당 프로세스의 주 스레드를 실행 중인 시작 됩니다. 가 되 면이 스레드를 종료 하는 프로세스입니다. 이 기본 스레드 함수 주소의 형태로 시작 코드에서 운영 체제에 제공 됩니다. 일반적으로의 주소는 **주** 또는 `WinMain` 제공 되는 함수입니다.  
  
 원하는 경우 응용 프로그램에서 추가 스레드를 만들 수 있습니다. 완료 되기를 기다려야 사용자 하지 않을 때 백그라운드 또는 유지 관리 작업을 처리 하 이렇게 할 수 있습니다. MFC 응용 프로그램의 모든 스레드가 표시 됩니다 [CWinThread](../mfc/reference/cwinthread-class.md) 개체입니다. 대부분의 경우에도 않아도 명시적으로 이러한 개체를 만드는; 프레임 워크 도우미 함수를 호출 하는 대신 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 만듦는 `CWinThread` 있습니다에 대 한 개체입니다.  
  
 두 가지 유형의 스레드를 구분 하는 MFC: 사용자 인터페이스 스레드와 작업자 스레드 수입니다. 사용자 인터페이스 스레드 이벤트와 사용자에 의해 생성 된 메시지에 응답 하 고 사용자 입력을 처리 하려면 일반적으로 사용 됩니다. 작업자 스레드 등의 작업을 다시 계산, 사용자 입력이 필요 하지 않은 완료 하려면 일반적으로 사용 됩니다. Win32 API 유형의 스레드; 간에 구분 되지 않습니다. 방금 스레드 실행을 시작할 수 있도록 스레드의 시작 주소를 알고 있어야 합니다. MFC는 메시지 펌프 사용자 인터페이스에서 이벤트를 제공 하 여 특수 사용자 인터페이스 스레드를 처리 합니다. `CWinApp` 한 예로 사용자 인터페이스 스레드 개체에서 파생 되므로 `CWinThread` 이벤트 및 사용자에 의해 생성 된 메시지를 처리 합니다.  
  
 여러 스레드에서 동일한 개체에 대 한 액세스를 필요할 수 있습니다 하는 경우에는 특별 한 주의 해야 합니다. [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md) 이러한 상황에서 발생할 수 있는 문제를 해결 하는 데 사용할 수 있는 기술에 설명 합니다. [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../parallel/multithreading-how-to-use-the-synchronization-classes.md) 단일 개체에 액세스 여러 스레드를 동기화에 사용할 수 있는 클래스를 사용 하는 방법을 설명 합니다.  
  
 작성 하 고 다중 스레드 프로그래밍을 디버깅은 기본적으로 복잡 하 고 까다로운 작업 개체는 액세스 하지 않도록 둘 이상의 스레드 한 번에 확인 해야 하기 때문에 있습니다. 제외 스레딩 항목 하는 기본적인 다중 스레드 프로그래밍, 다중 스레드 프로그램에서 MFC를 사용 하는 방법에 대해서만 설명 합니다. 기능 추가 및 MFC;에 포함 되지 않은 Win32 Api에 대 한 몇 가지 다중 스레드를 보여 주는 Visual c + +에 포함 된 다중 스레드 MFC 샘플 그러나 시작 지점이 될 하려는 합니다.  
  
 운영 체제 프로세스 및 스레드를 처리 하는 방법에 대 한 자세한 내용은 참조 [프로세스 및 스레드](http://msdn.microsoft.com/library/windows/desktop/ms684841) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
 MFC의 다중 스레딩과 지원에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   [다중 스레딩: 사용자 인터페이스 스레드 만들기](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [다중 스레딩: 작업자 스레드 만들기](../parallel/multithreading-creating-worker-threads.md)  
  
-   [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [다중 스레딩: 스레드 종료](../parallel/multithreading-terminating-threads.md)  
  
-   [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md)  
  
-   [다중 스레딩: 동기화 클래스 사용 시기](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## <a name="see-also"></a>참고 항목  
 [이전 코드를 위한 다중 스레드 지원(Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)