---
title: "특수 CWinApp 서비스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a12d9553e1519c158c0a0e9d2fcec6365b65fe
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="special-cwinapp-services"></a>특수 CWinApp 서비스
것 외에도 메시지 루프를 실행 하면 응용 프로그램을 초기화 하 고 그 뒤를 정리할 수 [CWinApp](../mfc/reference/cwinapp-class.md) 몇 가지 다른 서비스를 제공 합니다.  
  
##  <a name="_core_shell_registration"></a>셸 등록  
 기본적으로 MFC 응용 프로그램 마법사를 사용하면 파일 탐색기 또는 파일 관리자에서 두 번 클릭하여 응용 프로그램에서 생성된 데이터 파일을 열 수 있습니다. MFC 응용 프로그램 마법사에 대 한 호출 추가 응용 프로그램이 MDI 응용 프로그램이 고 응용 프로그램이 만드는 파일에 대 한 확장을 지정 하는 경우는 [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) 및 [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)의 멤버 함수 [CWinApp](../mfc/reference/cwinapp-class.md) 에 `InitInstance` 작성 재정의 합니다.  
  
 `RegisterShellFileTypes`는 사용자의 응용 프로그램 문서 형식을 파일 탐색기 또는 파일 관리자에 등록합니다. 이 함수는 Windows에서 유지 관리되는 등록 데이터베이스에 항목을 추가합니다. 항목은 각 문서 유형을 등록하고, 파일 확장자를 해당 파일 형식과 연결하고, 응용 프로그램을 열기 위한 명령줄을 지정하고, 해당 형식의 문서를 열기 위해 DDE(동적 데이터 교환) 명령을 지정합니다.  
  
 `EnableShellOpen`은 파일 탐색기 또는 파일 관리자에서 DDE 명령을 수신하도록 허용하여 프로세스를 완료하고 사용자가 선택한 파일을 엽니다.  
  
 `CWinApp`의 이러한 자동 등록 지원 덕분에 응용 프로그램에 .reg 파일을 포함하거나 특별한 설치 작업을 수행할 필요가 없습니다.  
  
 응용 프로그램에 대 한 GDI + 초기화 하려는 경우 (호출 하 여 [GdiplusStartup](https://msdn.microsoft.com/library/ms534077) 에 프로그램 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 함수), GDI + 백그라운드 스레드를 표시 하지 않아야 할 합니다.  
  
 설정 하 여이 수행할 수는 **SuppressBackgroundThread** 의 멤버는 [GdiplusStartupInput](https://msdn.microsoft.com/library/ms534067) 구조체 **TRUE**합니다. 때 GDI + 백그라운드 스레드를는 **NotificationHook** 및 **NotificationUnhook** 호출에서 수행 되도록 되기 직전 설정 및 응용 프로그램의 메시지 루프를 종료 합니다. 이러한 호출에 대 한 자세한 내용은 참조 하십시오. [GdiplusStartupOutput](https://msdn.microsoft.com/library/ms534068)합니다. 따라서 호출 하는 좋은 위치 **GdiplusStartup** 하 고 가상 함수 재정의에서 후크 알림 함수는 [cwinapp:: Run](../mfc/reference/cwinapp-class.md#run)다음과 같이 합니다.  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]  
  
 백그라운드 GDI+ 스레드를 숨기지 않으면, 해당 기본 창이 생성되기 전에 DDE 명령이 응용 프로그램에 너무 빨리 실행될 수 있습니다. 셸에서 실행된 DDE 명령은 중간에 중단되어 오류 메시지가 나타날 수 있습니다.  
  
##  <a name="_core_file_manager_drag_and_drop"></a>파일 관리자 끌어서 놓기  
 파일은 파일 관리자 또는 파일 탐색기의 파일 보기 창에서 응용 프로그램의 창으로 끌어 놓을 수 있습니다. 예를 들어 MDI 응용 프로그램의 기본 창에 하나 이상의 파일을 끌어 놓을 수 있도록 설정해야 할 수 있습니다. 여기에서 응용 프로그램은 해당 파일에 대한 파일 이름을 검색하고 MDI 자식 창을 열 수 있습니다.  
  
 MFC 응용 프로그램 마법사를 끌어서 파일을 사용 하려면 응용 프로그램에서 삭제에 대 한 호출을 기록는 [CWnd](../mfc/reference/cwnd-class.md) 멤버 함수 [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) 에서 주 프레임 창에 대 한 프로그램 `InitInstance`합니다. 끌어서 놓기 기능을 구현할 필요가 없으면 이 호출을 제거할 수 있습니다.  
  
> [!NOTE]
>  또한 OLE를 사용하면 문서 간 또는 문서 내에서의 데이터 끌기와 같은 보다 일반적인 끌어서 놓기 기능을 구현할 수도 있습니다. 내용은 문서를 참조 하십시오. [끌어서 놓기 (OLE)](../mfc/drag-and-drop-ole.md)합니다.  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a>일반적으로 외우는 가장 최근에 사용한 문서  
 사용자가 파일을 열고 닫을 때 응용 프로그램 개체는 최근에 사용된 4개 파일에 대한 추적을 유지합니다. 이러한 파일의 이름은 파일 메뉴에 추가되며 변경될 경우 업데이트됩니다. 프레임워크는 레지스트리 또는 .ini 파일에서 프로젝트와 동일한 이름을 사용해서 이러한 파일 이름을 저장하고, 응용 프로그램이 시작될 때 파일에서 이를 읽어옵니다. `InitInstance` MFC 응용 프로그램 마법사에 대 한 호출을 포함 만들어지는 재정의 [CWinApp](../mfc/reference/cwinapp-class.md) 멤버 함수 [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), 레지스트리 또는.ini에서 정보를 로드 파일을 최근에 가장을 포함 하 여 파일 이름이 사용 됩니다.  
  
 이러한 항목은 다음과 같이 저장됩니다.  
  
-   Windows NT, Windows 2000 이상에서 값은 레지스트리 키에 저장됩니다.  
  
-   Windows 3.x에서 값은 WIN.INI 파일에 저장됩니다.  
  
-   Windows 95 이상에서 값은 WIN.INI 의 캐시된 버전에 저장됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)