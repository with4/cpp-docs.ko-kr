---
title: "특수 CWinApp 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadStdProfileSettings"
  - "EnableShellOpen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 개체[C++], 서비스"
  - "CWinApp 클래스, 파일 관리자 끌어서 놓기"
  - "CWinApp 클래스, GDI+ 초기화"
  - "CWinApp 클래스, 최근 사용 문서"
  - "CWinApp 클래스, 서비스"
  - "CWinApp 클래스, 셸 등록"
  - "끌어서 놓기[C++], 파일"
  - "DragAcceptFiles 메서드"
  - "EnableShellOpen 메서드"
  - "파일[C++], 끌어서 놓기"
  - "파일[C++], 가장 최근 사용"
  - "GDI+, MFC에 대한 초기화"
  - "GDI+, 백그라운드 스레드 표시 안 함[MFC]"
  - "LoadStdProfileSettings 메서드"
  - "MFC[C++], 파일 작업"
  - "MFC[C++], 가장 최근에 사용한 파일 목록"
  - "MFC[C++], 셸 등록"
  - "MRU 목록"
  - "파일 형식 등록"
  - "RegisterShellFileTypes 메서드"
  - "등록[C++], 셸"
  - "레지스트리[C++], 가장 최근에 사용한 파일"
  - "서비스, CWinApp에서 제공"
  - "셸, 파일 형식 등록"
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 특수 CWinApp 서비스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메세지 루프를 실행하는 것과 응용 프로그램을초기화할 수 있는 기회를 제공하는것 뿐만아니라 그것을 정리할 수 있습니다. [CWinApp](../mfc/reference/cwinapp-class.md) 는 다양한 서비스를 제공합니다.  
  
##  <a name="_core_shell_registration"></a> 셸 등록  
 기본적으로 MFC 응용 프로그램 마법사는 쉽게 파일 탐색기나 파일 관리자에서 두 번 클릭 하여 응용 프로그램에서 만든 데이터 파일을 열 수 있습니다.  응용 프로그램이 MDK 응용 프로그램이고 응용 프로그램에서 만든 파일에 대한 확장명을 지정하는 경우, MFC 응용 프로그램 마법사는 [RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md) 에 호출을 추가하고 `InitInstance` 오버라이드에 [CWinApp](../mfc/reference/cwinapp-class.md) 의 [EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md) 멤버 함수를 추가합니다.  
  
 `RegisterShellFileTypes`는 파일 탐색기 또는 파일 관리자를 사용 하여 응용 프로그램의 문서 형식을 등록합니다.  함수는 Windows에서 관리 하는 등록 데이터베이스에 항목을 추가 합니다.  항목은 각 문서 형식을 등록, 파일 형식과 파일 확장명 연결, 명령줄에서 응용 프로그램을 지정 및 해당 형식의 문서를 동적 데이터 교환 \(DDE\) 명령을 지정 합니다.  
  
 `EnableShellOpen`는 응용 프로그램이 사용자가 선택한 파일을 열려면 파일 탐색기 또는 파일 관리자에서 DDE 명령을 받을 수 있도록 하여 프로세스를 완료 합니다.  
  
 `CWinApp` 에서 자동 등록 지원은 응용 프로그램이나 특별한 설치 작업을 사용하여 a .reg 파일을 이동시킬 필요를 없앱니다.  
  
 응용 프로그램에서 GDI\+를 초기화하려면 \([InitInstance](../Topic/CWinApp::InitInstance.md) 함수에서 [GdiplusStartup](_gdiplus_FUNC_GdiplusStartup_token_input_output_) 를 호출하여\) GDI\+ 배경 스레드를 억제해야 합니다.  
  
 **TRUE** 에 대한 [GdiplusStartupInput](_gdiplus_STRUC_GdiplusStartupInput) 구조체의 **SuppressBackgroundThread** 멤버를 설정하여 할수 있습니다.  GDI\+ 배경 스레드를 억제 할때, **NotificationHook** 및 **NotificationUnhook** 는 \([GdiplusStartupOutput](_gdiplus_STRUC_GdiplusStartupOutput) 를 참조하십시오\) 응용 프로그램의 메세지 루프에 진입하고 나오기 전 만들어져야 합니다.  그러므로, **GdiplusStartup**와 알림 후크 함수를 호출하기 좋은 위치는 [CWinApp::Run](../Topic/CWinApp::Run.md) 가상 함수의 재정의 안입니다. 다음을 보십시오.  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/CPP/special-cwinapp-services_1.cpp)]  
  
 GDI\+ 배경 스레드를 억제하는 경우, DDE 명령은 메인 창이 생성되기 전에 응용 프로그램에 대해 빨리 이슈될 수 있습니다.  셸에 의한 DDE 명령은 오류 메세지를 반환하며 중간에 중단될 수 있습니다.  
  
##  <a name="_core_file_manager_drag_and_drop"></a> 파일 관리자 끌어서 놓기  
 파일은 파일 관리자 또는 파일 탐색기에서 파일 보기 창으로 부터 응용 프로그램의 창으로 드래그 되어야 합니다.  예를 들어, MDI 응용 프로그램의 메인 창에 하나 이상의 파일이 드래그 될 수 있습니다. 이 때 응용 프로그램은 이 파일들에 대해 파일 이름을 추적하고 MDI 자식 창을 엽니다.  
  
 응용 프로그램에서 파일 드래그 앤 드롭을 사용하려면, MFC 응용 프로그램 마법사는 `InitInstance` 에서 메인 프래임 창에 대해[CWnd](../mfc/reference/cwnd-class.md) 멤버 함수[DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md) 에 대한 호출을 씁니다.  드래그 앤 드롭 기능 구현을 원하지 않으면 제거할 수 있습니다.  
  
> [!NOTE]
>  일반적인 드래그 앤 드롭을 구현할 수 있습니다\-또는 문서 내에서 데이터를 끕니다. \-OLE를 사용하여  더 자세한 정보는 [Drag and Drop \(OLE\)](../mfc/drag-and-drop-ole.md) 를 참조하십시오.  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> 최근에 사용한 문서의 추적을 유지합니다.  
 사용자가 파일을 열고 닫을 때, 응용 프로그램 개체는 가장 최근에 사용한 파일의 추적을 유지합니다.  이 파일의 이름은 파일 메뉴에 추가 되며 변경 될 경우 업데이트 됩니다.  프레임 워크는 레지스트리 또는.ini 파일을 프로젝트와 같은 이름 사용 하여 이 파일 이름을 저장 하고 응용 프로그램이 시작 될 때 해당 파일에서 읽습니다.  MFC 응용 프로그램 마법사가 생성한 `InitInstance` 오버라이드는 가장 최근에 사용된 파일을 포함하는 레지스트리 또는 .ini file 파일에서 정보를 로드하는 [CWinApp](../mfc/reference/cwinapp-class.md) 멤버 함수 [LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md) 에 대한 호출을 포함합니다.  
  
 이러한 항목은 다음과 같이 저장 됩니다.  
  
-   Windows NT, Windows 2000 및 이후에서 값은 레지스트리 키에 저장됩니다.  
  
-   Windows에서 3.x에서, 값은 WIN.INI 파일에 저장됩니다.  
  
-   Windows 95 및 이후에서,값은 WIN.INI 의 캐시된 버전에 저장됩니다.  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)