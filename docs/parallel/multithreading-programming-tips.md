---
title: "다중 스레딩: 프로그래밍 팁 | Microsoft Docs"
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
  - "액세스 제어[C++], 다중 스레딩"
  - "통신[C++], 스레드 간"
  - "임계 섹션[C++]"
  - "핸들 맵[C++]"
  - "다중 스레딩[C++], 프로그래밍 팁"
  - "비 MFC 스레드[C++]"
  - "개체[C++], 여러 스레드"
  - "프로그래밍[C++], 다중 스레드"
  - "동기화[C++], 다중 스레딩"
  - "스레딩[C++], 유용한 정보"
  - "스레딩[MFC], 프로그래밍 팁"
  - "문제 해결[C++], 다중 스레딩"
  - "Windows 핸들 맵[C++]"
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 다중 스레딩: 프로그래밍 팁
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다중 스레드 응용 프로그램은 데이터에 액세스할 때 단일 스레드 응용 프로그램보다 엄격한 주의가 필요합니다.  다중 스레드 응용 프로그램에서는 독립적인 여러 실행 경로가 동시에 사용되므로 알고리즘이나 데이터 또는 두 가지 모두 여러 스레드에서 동시에 데이터를 사용할 수 있다는 것을 인식해야 합니다.  이 항목에서는 MFC\(Microsoft Foundation Class\) 라이브러리를 사용하여 다중 스레드 응용 프로그램을 프로그래밍할 때 일어날 수 있는 문제를 방지할 수 있는 여러 가지 기법에 대해 설명합니다.  
  
-   [여러 스레드에서 개체 액세스](#_core_accessing_objects_from_multiple_threads)  
  
-   [MFC 형식이 아닌 스레드에서 MFC 개체 액세스](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [Windows 핸들 맵](#_core_windows_handle_maps)  
  
-   [스레드 사이의 통신](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> 여러 스레드에서 개체 액세스  
 크기와 성능상의 이유로 MFC 개체는 개체 수준이 아니라 클래스 수준에서만 스레드 안전을 보장할 수 있습니다.  이것은 두 개의 스레드가 두 개의 다른 `CString` 개체를 조작할 수는 있지만 동일한 `CString` 개체를 조작할 수는 없음을 의미합니다.  반드시 여러 스레드에서 동일한 개체를 조작해야 하는 경우 적절한 Win32 동기화 메커니즘\(예: 임계 섹션\)을 사용하여 이러한 액세스를 보호하십시오.  임계 영역 및 기타 관련 개체에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)을 참조하십시오.  
  
 클래스 라이브러리는 내부적으로 임계 섹션을 사용하여 디버그 메모리 할당에서 사용되는 것과 같은 전역 데이터 구조체를 보호합니다.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> MFC 형식이 아닌 스레드에서 MFC 개체 액세스  
 [CWinThread](../mfc/reference/cwinthread-class.md) 개체를 사용하는 방법말고 다른 방법으로 스레드를 만드는 다중 스레드 응용 프로그램의 경우 해당 스레드에서 다른 MFC 개체에 액세스할 수 없습니다.  즉 보조 스레드에서 어떤 MFC 개체에 액세스하려면 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../parallel/multithreading-creating-user-interface-threads.md) 또는 [다중 스레딩: 작업자 스레드 만들기](../parallel/multithreading-creating-worker-threads.md)에서 설명한 방법 중 하나를 사용하여 해당 스레드를 만들어야 합니다.  클래스 라이브러리에서 다중 스레드 응용 프로그램을 처리하는 데 필요한 내부 변수를 초기화하려면 이 방법을 사용해야 합니다.  
  
##  <a name="_core_windows_handle_maps"></a> Windows 핸들 맵  
 일반적으로 스레드는 자신이 만든 MFC 개체만 액세스할 수 있습니다.  이는 여러 스레드에서 동시에 액세스할 수 없도록 스레드 로컬 저장소에 임시 및 영구 Windows 핸들 맵을 보관하기 때문입니다.  예를 들어, 작업자 스레드는 계산을 수행한 다음 문서의 `UpdateAllViews` 멤버 함수를 호출하여 새 데이터에 대한 뷰를 포함하는 창을 수정할 수 없습니다.  `CWnd` 개체에서 `HWND`로의 매핑은 주 스레드에 대해 로컬이므로 이 작업은 아무 효과가 없습니다.  이것은 한 스레드에서는 Windows 핸들을 C\+\+ 개체로 매핑할 수 있지만 다른 스레드에서는 동일한 핸들이 다른 C\+\+ 개체로 매핑될 수 있음을 의미합니다.  한 스레드에서 변경한 내용은 다른 스레드에 반영되지 않습니다.  
  
 이 문제를 해결할 수 있는 여러 가지 방법이 있습니다.  첫째 방법은 C\+\+ 개체가 아니라 개별 핸들\(예: `HWND`\)을 작업자 스레드에 전달하는 것입니다.  그러면 작업자 스레드가 적절한 `FromHandle` 멤버 함수를 호출하여 이들 개체를 임시 맵에 추가합니다.  또한 **Attach**를 호출하여 개체를 스레드의 영구 맵에 추가할 수 있지만 이 방법은 개체가 스레드보다 오래 존재할 경우에만 사용해야 합니다.  
  
 다른 방법은 작업자 스레드에서 수행하는 다른 작업에 해당하는 새 사용자 정의 메시지를 만든 다음 **::PostMessage**를 사용하여 응용 프로그램의 주 창에 이들 메시지를 게시하는 것입니다.  이 통신 방법은 두 스레드가 모두 동일한 주소 공간에서 실행된다는 점을 제외하면 두 개의 다른 응용 프로그램 사이의 통신 방법과 유사합니다.  
  
 핸들 매핑에 대한 자세한 내용은 [Technical Note 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md)을 참조하십시오.  스레드 로컬 저장소에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686749) 및 [Using Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686991)를 참조하십시오.  
  
##  <a name="_core_communicating_between_threads"></a> 스레드 사이의 통신  
 MFC는 스레드가 개체에 대한 액세스를 동기화하여 스레드 안전을 유지할 수 있게 하는 여러 클래스를 제공합니다.  이들 클래스의 사용 방법에 대해서는 [다중 스레딩: 동기화 클래스 사용 방법](../parallel/multithreading-how-to-use-the-synchronization-classes.md) 및 [다중 스레딩: 동기화 클래스 사용 시기](../parallel/multithreading-when-to-use-the-synchronization-classes.md)에서 자세히 설명합니다.  이러한 개체에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353)을 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)