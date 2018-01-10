---
title: "MFC 프로그램 또는 컨트롤 소스 및 헤더 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], MFC source and header
ms.assetid: f61419a8-bf69-4bbb-8f7c-1734be5e6db6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adb4ba4fdcc141438b2eeb87b4e3c9151bb9a5c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-program-or-control-source-and-header-files"></a>MFC 프로그램 또는 컨트롤 소스 및 헤더 파일
만들 프로젝트에 대 한 선택 옵션에 따라 Visual Studio에서 MFC 프로젝트를 만들 때에 다음 파일이 생성 됩니다. 프로젝트에 포함 된 예를 들어 *Projname*dlg.cpp 및 *Projname*dlg.h 파일 대화 상자 기반 프로젝트 또는 클래스를 만드는 경우에 합니다.  
  
 에 살고 있는 모든이 파일은 *Projname* 디렉터리 및 헤더 (.h) 파일 폴더 또는 솔루션 탐색기에서 소스 파일 (.cpp 파일) 폴더에 있습니다.  
  
|파일 이름|설명|  
|---------------|-----------------|  
|*Projname*.h|프로그램 또는 DLL에 대 한 주 포함 파일입니다. 모든 전역 기호를 포함 하 고 `#include` 다른 헤더 파일에 대 한 지시문입니다. 파생 된 `CPrjnameApp` 에서 클래스 `CWinApp` 선언 하 고는 `InitInstance` 멤버 함수입니다. 컨트롤의 경우는 `CPrjnameApp` 클래스에서 파생 된 `COleControlModule`합니다.|  
|*Projname*.cpp|주 프로그램 소스 파일입니다. 클래스의 한 개체를 만듭니다 `CPrjnameApp`에서 파생 된 `CWinApp`, 재정의 `InitInstance` 멤버 함수입니다.<br /><br /> 실행 파일의 경우 `CPrjnameApp::InitInstance` 여러 작업을 수행 합니다. 문서 및 뷰; 사이의 연결 역할을 하는 문서 템플릿을 등록합니다 주 프레임 창을; 만듭니다. 및 빈 문서를 만듭니다 (또는 응용 프로그램에 명령줄 인수로 지정 된 경우 문서를 열고).<br /><br /> Dll 및 (이전의 OLE) ActiveX 컨트롤, `CProjNameApp::InitInstance` ole 컨트롤의 개체 팩터리를 호출 하 여 등록 `COleObjectFactory::RegisterAll` 를 호출 하 고 `AfxOLEInit`합니다. 또한 멤버 함수 `CProjNameApp::ExitInstance` 컨트롤을 호출 하 여 메모리에서 언로드 데 **AfxOleTerm**합니다.<br /><br /> 이 파일에서 또한 등록 하 고 구현 하 여 Windows 등록 데이터베이스에 컨트롤을 등록 취소는 `DllRegisterServer` 및 `DllUnregisterServer` 함수입니다.|  
|*Projname*ctrl.h, *Projname*ctrl.cpp|선언 하 고 구현 된 `CProjnameCtrl` 클래스입니다. `CProjnameCtrl`파생 된 `COleControl`, 초기화, 그리기 및 serialize 하는 일부 멤버 함수의 기본 구현을 정의 됩니다 (로드 및 저장) 컨트롤입니다. 메시지, 이벤트 및 디스패치 맵 정의 됩니다.|  
|*Projname*dlg.cpp, *Projname*dlg.h|대화 상자 기반 응용 프로그램을 선택한 경우에 생성 합니다. 파일에서 파생 하 라는 대화 상자 클래스를 구현 `CProjnameDlg`, 대화 상자를 초기화 하 고 대화 상자 데이터 교환 (DDX)를 수행 하는 기본 멤버 함수를 포함 합니다. 에 대 한 대화 상자 클래스 대신 이러한 파일에도 나타나므로 *Projname*.cpp 합니다.|  
|Dlgproxy.cpp, Dlgproxy.h|대화 상자 기반 프로그램, 구현 및 헤더 파일에 기본 대화 상자에 대 한 프로젝트의 자동화 프록시 클래스에 대 한 합니다. 이 자동화 지원을 선택한 경우에 사용 됩니다.|  
|*Projname*doc.cpp, *Projname*doc.h|파생 하 라는 문서 클래스를 구현 `CProjnameDoc`, 기본 멤버 함수는 문서를 초기화, serialize를 포함 하 고 (저장 및 로드) 문서 및 디버깅 진단을 구현 합니다.|  
|*Projname*set.h/.cpp|데이터베이스를 지원 하 고 레코드 집합 클래스를 포함 하는 프로그램을 만드는 경우를 생성 합니다.|  
|*Projname*view.cpp, *Projname*view.h|파생 하는 뷰 클래스를 구현 `CProjnameView`를 표시 하 고 문서 데이터 인쇄 사용 되는 합니다. `CProjnameView` 클래스 다음 MFC 클래스 중 하나에서 파생 됩니다.<br /><br /> -   [CEditView](../mfc/reference/ceditview-class.md)<br />-   [CFormView](../mfc/reference/cformview-class.md)<br />-   [CRecordView](../mfc/reference/crecordview-class.md)<br />-   [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)<br />-   [CTreeView](../mfc/reference/ctreeview-class.md)<br />-   [CListView](../mfc/reference/clistview-class.md)<br />-   [CRichEditView](../mfc/reference/cricheditview-class.md)<br />-   [CScrollView](../mfc/reference/cscrollview-class.md)<br />-   [CView](../mfc/reference/cview-class.md)<br />-   [CHTMLView](../mfc/reference/chtmlview-class.md)<br />-   [CHTMLEditView](../mfc/reference/chtmleditview-class.md)<br /><br /> 프로젝트의 뷰 클래스 뷰 및 디버깅 진단을 구현 그리는 기초 멤버 함수를 포함 합니다. 인쇄에 대 한 지원을 사용 하는 경우 메시지 맵 항목 인쇄, 인쇄 설정에 대 한 추가 및 미리 보기 명령 메시지를 인쇄 합니다. 이러한 항목 기본 뷰 클래스에서 해당 멤버 함수를 호출합니다.|  
|*Projname*PropPage.h, *Projname*PropPage.cpp|선언 하 고 구현 된 `CProjnamePropPage` 클래스입니다. `CProjnamePropPage`파생 된 `COlePropertyPage` 기초 멤버 함수 `DoDataExchange`, 데이터 교환 및 유효성 검사를 구현 하기 위해 제공 됩니다.|  
|IPframe.cpp, IPframe.h|응용 프로그램 마법사에서 미니 서버 또는 전체 서버 옵션을 선택 하는 경우 만든 **자동화 옵션** (3/6 단계) 페이지. 파일 파생 하 여 명명 된 내부 프레임 창 클래스를 구현할 **CInPlaceFrame**, 서버는 컨테이너 프로그램에 의해 활성화 될 때 사용 합니다.|  
|Mainfrm.cpp, Mainfrm.h|파생 된 **CMainFrame** 클래스 중 하나에서 [CFrameWnd](../mfc/reference/cframewnd-class.md) (SDI 응용 프로그램)에 대 한 또는 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) (MDI 응용 프로그램)에 대 한 합니다. **CMainFrame** 클래스 응용 프로그램 마법사에서 해당 옵션을 선택한 경우 도구 모음 단추 및 상태 표시줄의 생성을 처리 **응용 프로그램 옵션** (6의 4 단계) 페이지. 사용 하 여에 대 한 내용은 **CMainFrame**, 참조 [응용 프로그램 마법사로 만든 프레임 창 클래스](../mfc/frame-window-classes-created-by-the-application-wizard.md)합니다.|  
|Childfrm.cpp, Childfrm.h|파생 된 **CChildFrame** 에서 클래스 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)합니다. **CChildFrame** 클래스 MDI 문서 프레임 창에 사용 됩니다. 이러한 파일은 MDI 옵션을 선택 하는 경우에 항상 만들어집니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [ATL 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/atl-program-or-control-source-and-header-files.md)   
 [CLR 프로젝트](../ide/files-created-for-clr-projects.md)