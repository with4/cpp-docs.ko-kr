---
title: "다중 스레딩: 프로그래밍 팁 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], programming tips
- handle maps [C++]
- access control [C++], multithreading
- objects [C++], multiple threads and
- non-MFC threads [C++]
- threading [MFC], programming tips
- critical sections [C++]
- synchronization [C++], multithreading
- programming [C++], multithreaded
- communications [C++], between threads
- threading [C++], best practices
- troubleshooting [C++], multithreading
- Windows handle maps [C++]
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30ecf45c8a22dfb42917affa59152aeefbc35425
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-programming-tips"></a>다중 스레딩: 프로그래밍 팁
다중 스레드 응용 프로그램 데이터에 액세스할 때 단일 스레드 응용 프로그램 보다 엄격한 주의가 필요 합니다. 에 있기 때문에 여러 개의 독립 실행 경로가에서 동시에 사용 다중 스레드 응용 프로그램 알고리즘, 데이터, 또는 둘 다 알아야 할 데이터를 한 번에 둘 이상의 스레드에서 사용할 수 없습니다. 이 항목에서는 Microsoft Foundation 클래스 (MFC) 라이브러리와 다중 스레드 응용 프로그램을 프로그래밍할 때 발생할 수 있는 문제를 방지 하는 방법에 설명 합니다.  
  
-   [여러 스레드에서 개체 액세스](#_core_accessing_objects_from_multiple_threads)  
  
-   [비 MFC 스레드에서 MFC 개체 액세스](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [Windows 핸들 맵](#_core_windows_handle_maps)  
  
-   [스레드 간 통신](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a>여러 스레드에서 개체 액세스  
 크기와 성능 이유로 MFC 개체가 않습니다 스레드로부터 안전한 클래스 수준에만 개체 수준. 즉, 서로 다른 두 조작 하는 두 개의 별도 스레드는 있음을 `CString` 개체가 아니라 두 스레드는 제외 동일한 조작 `CString` 개체입니다. 임계 영역 등의 적절 한 Win32 동기화 메커니즘과 반드시 동일한 개체를 조작 하는 여러 스레드 있어야 하는 경우 이러한 액세스를 보호 합니다. 임계 영역 및 기타에 대 한 자세한 내용은 관련 개체가 참조 [동기화](http://msdn.microsoft.com/library/windows/desktop/ms686353) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
 클래스 라이브러리는 임계 영역 디버그 메모리 할당에 의해 사용 되는 전역 데이터 구조를 보호 하기 위해 내부적으로 사용 합니다.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a>비 MFC 스레드에서 MFC 개체 액세스  
 스레드를 사용 하 여 이외의 방식으로 만드는 다중 스레드 응용 프로그램의 경우는 [CWinThread](../mfc/reference/cwinthread-class.md) 개체를 해당 스레드에서 다른 MFC 개체를 액세스할 수 없습니다. 즉, 보조 스레드에서 모든 MFC 개체에 액세스 하려는 경우 만들어야 해당 스레드에 설명 된 방법 중 하나로 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../parallel/multithreading-creating-user-interface-threads.md) 또는 [다중 스레딩: 작업자 스레드 만들기](../parallel/multithreading-creating-worker-threads.md)합니다. 이러한 메서드는 다중 스레드 응용 프로그램을 처리 하는 데 필요한 내부 변수를 초기화 하는 클래스 라이브러리를 사용할 수 있는 뿐입니다.  
  
##  <a name="_core_windows_handle_maps"></a>Windows 핸들 맵  
 스레드는 일반적으로 만든 MFC 개체만 액세스할 수 있습니다. 즉, 임시 및 영구 Windows 핸들 맵 여러 스레드에서 동시 액세스 로부터 보호를 유지 하기 위해 스레드 로컬 저장소에 유지 됩니다. 예를 들어 작업자 스레드 한 계산을 수행할 수 없으며 다음 문서를 호출 `UpdateAllViews` 는 창을 수정 하 여 새 데이터에 대 한 뷰를 포함 하는 멤버 함수입니다. 이 구문은 아무 효과가 전혀 때문에에서 지도 `CWnd` 개체를 `HWND`s 주 스레드에 로컬입니다. 즉, 하나의 스레드를 c + + 개체에 대 한 창 핸들에서 매핑을 할 수 있지만 다른 스레드를 다른 c + + 개체는 동일한 핸들이 매핑할 수 있습니다. 스레드 하나에서 변경 내용을 다른에 반영 되지 것입니다.  
  
 여러 가지 방법으로이 문제를 해결 합니다. 첫 번째 개별 핸들을 전달 하는 (예:는 `HWND`) 작업자 스레드에 대 한 c + + 개체 보다 합니다. 작업자 스레드가 추가 다음 적절 한 호출 하 여 이러한 개체를를 임시 맵에 `FromHandle` 멤버 함수입니다. 호출 하 여 개체를 스레드 영구 맵에 추가할 수도 있습니다 **연결**, 하지만 개체가 스레드보다 더 이상 있을 경우에 수행 해야 합니다.  
  
 또 다른 방법은 해당 작업자 스레드 수행 되며 응용 프로그램의 주 창에 이러한 메시지를 게시 하는 다른 작업 하는 새 사용자 정의 메시지를 만든를 사용 하 여 **:: PostMessage**합니다. 통신의이 메서드는 두 개의 다른 응용 프로그램 두 스레드는 같은 주소 공간에서 실행 되는 제외 하 고 사이의 비슷합니다.  
  
 핸들 맵에 대 한 자세한 내용은 참조 [기술 참고 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md)합니다. 스레드 로컬 저장소에 대 한 자세한 내용은 참조 [스레드 로컬 저장소](http://msdn.microsoft.com/library/windows/desktop/ms686749) 및 [스레드 로컬 저장소를 사용 하 여](http://msdn.microsoft.com/library/windows/desktop/ms686991) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
##  <a name="_core_communicating_between_threads"></a>스레드 간 통신  
 MFC는 다양 한 스레드 안전을 유지할 수 있는 개체에 대 한 액세스를 동기화 하 여 사용할 수 있는 클래스를 제공 합니다. 이러한 클래스의 사용에 설명 되어 [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md) 및 [다중 스레딩: 동기화 클래스를 사용 하는 경우](../parallel/multithreading-when-to-use-the-synchronization-classes.md)합니다. 이러한 개체에 대 한 자세한 내용은 참조 [동기화](http://msdn.microsoft.com/library/windows/desktop/ms686353) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)