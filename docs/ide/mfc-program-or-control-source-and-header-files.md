---
title: "MFC 프로그램 또는 컨트롤 소스 및 헤더 파일 | Microsoft Docs"
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
  - "파일 형식[C++], MFC 소스 및 헤더"
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC 프로그램 또는 컨트롤 소스 및 헤더 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음은 Visual Studio에서 MFC 프로젝트를 만들 때 사용자가 선택하는 옵션에 따라 만들어지는 파일입니다.  예를 들어 대화 상자를 기반으로 하는 프로젝트 또는 클래스를 만드는 경우에만 *Projname*dlg.cpp 및 *Projname*dlg.h 파일이 프로젝트에 포함됩니다.  
  
 이 파일들은 모두 *Projname* 디렉터리에 저장되며 솔루션 탐색기의 헤더 파일\(.h 파일\) 폴더 또는 소스 파일\(.cpp 파일\) 폴더 중 하나에 들어 있습니다.  
  
|파일 이름|설명|  
|-----------|--------|  
|*Projname*.h|프로그램 또는 DLL을 위한 주 포함 파일.  다른 헤더 파일을 위한 모든 전역 기호와 `#include` 지시문이 들어 있습니다.  `CWinApp`에서 `CPrjnameApp` 클래스를 파생시키고 `InitInstance` 멤버 함수를 선언합니다.  컨트롤의 경우 `CPrjnameApp` 클래스는 `COleControlModule`에서 파생됩니다.|  
|*Projname*.cpp|주 프로그램 소스 파일.  `CWinApp`에서 파생된 `CPrjnameApp` 클래스의 한 개체를 만들고 `InitInstance` 멤버 함수를 재정의합니다.<br /><br /> 실행 파일의 경우 `CPrjnameApp::InitInstance`는 여러 가지 작업을 수행합니다.  문서와 뷰 사이의 연결 역할을 하는 문서 템플릿을 등록하고, 메인프레임 창을 만들며, 빈 문서를 만듭니다. 또는 응용 프로그램에 대한 명령줄 인수로 지정된 문서를 엽니다.<br /><br /> DLL 및 ActiveX\(이전의 OLE\) 컨트롤의 경우 `CProjNameApp::InitInstance`는 `COleObjectFactory::RegisterAll`을 호출하여 컨트롤의 개체 팩터리를 OLE와 함께 등록하고 `AfxOLEInit`을 호출합니다.  그 외에 멤버 함수인 `CProjNameApp::ExitInstance`는 **AfxOleTerm**을 호출하고 메모리에서 컨트롤을 언로드하는 데 사용됩니다.<br /><br /> 또한 이 파일은 `DllRegisterServer` 및 `DllUnregisterServer` 함수를 구현하여 Windows 등록 데이터베이스에 컨트롤을 등록하거나 등록을 취소합니다.|  
|*Projname*ctrl.h, *Projname*ctrl.cpp|`CProjnameCtrl` 클래스를 선언하고 구현합니다.  `CProjnameCtrl`dms `COleControl`에서 파생되며, 컨트롤 초기화, 그리기 및 serialize\(로드 및 저장\)를 수행하는 일부 멤버 함수의 기초 구현이 정의됩니다.  메시지, 이벤트 및 디스패치 맵도 정의됩니다.|  
|*Projname*dlg.cpp, *Projname*dlg.h|대화 상자를 기반으로 하는 응용 프로그램을 선택한 경우 만들어집니다.  이 파일은 `CProjnameDlg`라는 이름의 대화 상자 클래스를 파생하여 구현하고, 대화 상자를 초기화하는 기초 멤버 함수를 포함하며, 대화 상자 데이터 교환\(DDX\)을 수행합니다.  정보 대화 상자 클래스도 *Projname*.cpp 대신 이 파일에 포함됩니다.|  
|Dlgproxy.cpp, Dlgproxy.h|대화 상자를 기반으로 하는 프로그램에서 주 대화 상자를 위한 프로젝트의 자동화 프록시 클래스용 구현 파일 및 헤더 파일.  이것은 자동화 지원이 선택된 경우에만 사용됩니다.|  
|*Projname*doc.cpp, *Projname*doc.h|`CProjnameDoc`라는 이름의 문서 클래스를 파생하여 구현하며, 문서를 초기화하고, serialize\(저장 및 로드\)하며 디버깅 진단을 구현하는 기초 멤버 함수를 포함합니다.|  
|*Projname*set.h\/.cpp|데이터베이스를 지원하고 레코드 집합 클래스를 포함하는 프로그램을 만드는 경우 만들어집니다.|  
|*Projname*view.cpp, *Projname*view.h|문서 데이터를 화면에 표시하고 인쇄하는 데 사용되는 `CProjnameView`라는 뷰 클래스를 파생하여 구현합니다.  `CProjnameView` 클래스는 다음 MFC 클래스 중 하나에서 파생됩니다.<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> 프로젝트의 뷰 클래스는 뷰를 그리고, 디버깅 진단을 구현하는 기초 멤버 함수를 포함합니다.  인쇄 지원을 활성화하면 인쇄, 인쇄 설정, 인쇄 미리 보기 명령 메시지에 메시지 맵 항목이 추가됩니다.  이 항목들은 기본 뷰 클래스의 해당 멤버 함수를 호출합니다.|  
|*Projname*PropPage.h, *Projname*PropPage.cpp|`CProjnamePropPage` 클래스를 선언하고 구현합니다.  `CProjnamePropPage`는 `COlePropertyPage`에서 파생되며, 데이터 교환 및 유효성 검사를 구현하는 기초 멤버 함수인 `DoDataExchange`가 제공됩니다.|  
|IPframe.cpp, IPframe.h|응용 프로그램 마법사의 **자동화 옵션** 페이지\(6단계 중 3단계\)에서 미니 서버 또는 풀 서버 옵션을 선택한 경우 만들어집니다.  이 파일은 서버가 컨테이너 프로그램에 의해 그 자리에서 활성화될 때 사용되는 **CinPlaceFrame**이라는 현재 위치의 프레임 창 클래스를 파생하여 구현합니다.|  
|Mainfrm.cpp, Mainfrm.h|[CFrameWnd](../mfc/reference/cframewnd-class.md)\(SDI 응용 프로그램의 경우\) 또는 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)\(MDI 응용 프로그램의 경우\)에서 **CMainFrame** 클래스를 파생합니다.  **CMainFrame** 클래스는 응용 프로그램 마법사의 **응용 프로그램 옵션** 페이지\(6단계 중 4단계\)에서 해당 옵션을 선택한 경우 도구 모음 단추와 상태 표시줄 만들기를 처리합니다.  **CMainFrame** 사용에 대한 자세한 내용은 [응용 프로그램 마법사로 만든 프레임 창 클래스](../mfc/frame-window-classes-created-by-the-application-wizard.md)를 참조하십시오.|  
|Childfrm.cpp, Childfrm.h|[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)에서 **CChildFrame** 클래스를 파생합니다.  **CChildFrame** 클래스는 MDI 문서 프레임 창에 사용됩니다.  이 파일은 항상 MDI 옵션을 선택한 경우에만 만들어집니다.|  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR 프로젝트](../ide/files-created-for-clr-projects.md)