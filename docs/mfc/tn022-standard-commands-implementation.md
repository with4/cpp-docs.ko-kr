---
title: 'TN022: 표준 명령 구현 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.commands
dev_langs:
- C++
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dea42f4bd33281e65696791677bdd81a921a59e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385527"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: 표준 명령 구현
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트에서는 MFC 2.0에서 제공 하는 표준 명령 구현을 설명 합니다. 읽기 [기술 참고 21](../mfc/tn021-command-and-message-routing.md) 첫 번째 하므로 여러 표준 명령 구현 하는 데 사용 하는 메커니즘을 설명 합니다.  
  
 이 설명에서는 MFC 아키텍처, Api 및 일반적으로 프로그래밍 지식이 있다고 가정 합니다. 문서화 된으로 문서화 되지 않은 "구현만" Api 설명 되어 있습니다. 기능 또는 mfc에서 프로그래밍 하는 방법에 대 한 학습 하는 출발점이 아닙니다. 일반 정보 및 문서화 된 Api의 세부 정보에 대 한 Visual c + +를 참조 하십시오.  
  
## <a name="the-problem"></a>문제  
 MFC는 AFXRES 헤더 파일에 여러 표준 명령 Id를 정의합니다. 8. 이러한 명령에 대해 지원 되는 프레임 워크 다릅니다. 프레임 워크 클래스 이러한 명령을 처리 위치와 방법을 이해 합니다 보여 줄 뿐만 아니라 어떻게 프레임 워크 내부적으로 작동 하지만 표준 구현 사용자 지정 하 고 구현 하기 위한 몇 가지 기법을 설명 하는 방법에 유용한 정보가 제공 됩니다. 사용자 고유의 명령 처리기입니다.  
  
## <a name="contents-of-this-technical-note"></a>이 기술 노트의 내용  
 각 명령 ID는 두 개의 섹션에 설명 되어 있습니다.  
  
-   제목: 명령 ID의 심볼 이름 (예를 들어 **ID_FILE_SAVE**) 뒤에 콜론으로 구분 하는 명령 (예: "현재 문서 저장")의 용도입니다.  
  
-   명령 및 기본 구현에서 수행 하는 작업을 구현 하는 클래스를 설명 하는 하나 이상의 단락  
  
 대부분의 기본 명령 구현 프레임 워크의 기본 클래스 메시지 맵에 prewired 됩니다. 파생된 클래스에서 명시적 배선 해야 하는 일부 명령 구현 있습니다. 이러한 "Note" 아래에서 설명 합니다. 응용 프로그램 마법사에서 오른쪽 옵션을 선택한 경우 이러한 기본 처리기를 생성 된 기본 응용 프로그램에 연결 됩니다.  
  
## <a name="naming-convention"></a>명명 규칙  
 표준 명령 가능 하면 사용 하는 것이 좋습니다 하는 간단한 명명 규칙을 따릅니다. 대부분의 표준 명령의 표준 위치에서 응용 프로그램의 메뉴 모음에 있습니다. 이 명령은의 심볼 이름인 "ID_" 메뉴 항목 이름을 다음 표준 팝업 메뉴 이름으로 시작 합니다. 기호 이름은 밑줄 단어 분리와 대문자입니다. 표준 메뉴 항목 이름 없는 명령에 대 한 논리적 명령 이름 "ID_"로 시작 정의 됩니다 (예를 들어 **ID_NEXT_PANE**).  
  
 접두사 "ID_"은 메뉴 항목, 도구 모음 단추 또는 다른 명령 사용자 인터페이스 개체에 바인딩할 수 있도록 하는 명령을 나타내는 데 사용 합니다. "ID_" 명령 처리 명령 처리기를 사용 해야는 `ON_COMMAND` 및 `ON_UPDATE_COMMAND_UI` 메커니즘은 MFC의 아키텍처를 명령입니다.  
  
 명령 아키텍처 및 활성화 하 고 사용 하지 않도록 메뉴 관련 코드가 필요 하지 않는 메뉴 항목에 대 한 표준 "IDM_" 접두사를 사용 하는 것이 좋습니다. 물론 MFC 명령 아키텍처에 따라 하면 명령 처리기가 보다 강력한 (도구 모음에 부합 한다고) 이후 뿐 아니라 명령 처리기 코드를 다시 사용할 수 있는 사용 하면 되므로 특정 메뉴 명령의 수는 작은 되어야 합니다.  
  
## <a name="id-ranges"></a>ID 범위  
 참조 하십시오 [Technical Note 20](../mfc/tn020-id-naming-and-numbering-conventions.md) 에 대 한 자세한 내용은 MFC의 ID 범위를 사용 합니다.  
  
 MFC 표준 명령 0xE000를 0xEFFF 범위에 속합니다. 하십시오 의존 하지 마십시오 이러한 Id의 특정 값 라이브러리의 이후 버전에서 변경 될 수 있기 때문입니다.  
  
 응용 프로그램 범위의 0x8000 ~ 0xDFFF은 명령을 정의 해야 합니다.  
  
## <a name="standard-command-ids"></a>표준 명령 Id  
 각 명령 ID에 대 한 표준 메시지 줄 프롬프트 문자열을 파일 표시 되는 메시지에서 찾을 수 있습니다. RC입니다. 해당 메뉴 프롬프트 문자열 ID 해야 큐브와 같아야 명령 id입니다.  
  
-   ID_FILE_NEW/비어 있는 새 문서를 만듭니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     `CWinApp::OnFileNew` 응용 프로그램에서이 명령을 문서 서식 파일의 수에 따라 다르게 구현합니다. 하나만 있으면 `CDocTemplate`, `CWinApp::OnFileNew` 적절 한 프레임 및 보기 클래스 뿐만 아니라 해당 유형의 새 문서를 만듭니다.  
  
     둘 이상 있는 경우 `CDocTemplate`, `CWinApp::OnFileNew` 묻는 대화 상자가 표시 되면서 됩니다 (**AFX_IDD_NEWTYPEDLG**) 이러한 사용할 문서 유형을 선택 합니다. 선택한 `CDocTemplate` 문서를 만드는 데 사용 됩니다.  
  
     일반적인 한 사용자 지정 `ID_FILE_NEW` 다른 및 문서 종류의 그래픽 더 많은 선택 옵션이 제공 하는 것입니다. 이 경우 구현할 수 있습니다 직접 **CMyApp::OnFileNew** 대신 메시지 맵에 배치 `CWinApp::OnFileNew`합니다. 기본 클래스 구현을 호출 하지 않아도가 됩니다.  
  
     또 다른 일반적인 사용자 지정 `ID_FILE_NEW` 각 형식의 문서를 만들기 위한 별도 명령에 제공 하는 것입니다. 이 경우 새 명령 Id, 예를 들어 ID_FILE_NEW_CHART 고 ID_FILE_NEW_SHEET 정의 해야 합니다.  
  
-   ID_FILE_OPEN 기존 문서를 엽니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     `CWinApp::OnFileOpen` 매우 간단한 구현을 호출 **CWinApp::DoPromptFileName** 이어서 `CWinApp::OpenDocumentFile` 파일 또는 경로 이름으로 열 파일입니다. `CWinApp` 구현 루틴 **DoPromptFileName** 표준 FileOpen 대화 상자를 시작 하 고 현재 문서 서식 파일에서 가져온 파일 확장명으로 채웁니다.  
  
     일반적인 한 사용자 지정 `ID_FILE_OPEN` FileOpen 대화 상자를 사용자 지정 하거나 추가 파일 필터를 추가 하는 것입니다. 기본 구현에서는 사용자 고유의 FileOpen 대화 상자를 닫고 호출으로 바꾸려면이 사용자 정의 하는 권장된 방법은 `CWinApp::OpenDocumentFile` 문서의 파일 또는 경로 이름을 사용 합니다. 기본 클래스를 호출할 필요가 없습니다 있습니다.  
  
-   ID_FILE_CLOSE 현재 열려 있는 문서를 닫습니다.  
  
     **CDocument::OnFileClose** 호출 `CDocument::SaveModified` 수정 된 다음 호출 하는 경우 문서를 저장 하 라는 메시지를 `OnCloseDocument`합니다. 수행 됩니다, 문서를 소멸을 포함 하 여, 모든 닫는 논리는 `OnCloseDocument` 루틴입니다.  
  
    > [!NOTE]
    >  **ID_FILE_CLOSE** 에서 다르게 역할을 `WM_CLOSE` 메시지 또는 **SC_CLOSE** 문서 프레임 창에 전달 하는 시스템 명령입니다. 경우에 있는 문서를 보여 주는 마지막 프레임 창의 창을 닫으면 문서를 닫습니다 됩니다. 사용 하 여 문서를 닫으면 **ID_FILE_CLOSE** 만 문서를 닫지 것입니다 이지만 문서를 보여 주는 모든 프레임 창을 종료 됩니다.  
  
-   ID_FILE_SAVE 현재 문서를 저장합니다.  
  
     도우미 루틴을 사용 하 여 구현 **CDocument::DoSave** 둘 다에 사용 되는 **OnFileSave** 및 **OnFileSaveAs**합니다. 하기 전에 저장 되지 않은 문서를 저장 하는 경우 (즉, 없기 경로 이름을 사용할 경우 FileNew의 경우) 또는 읽기 전용으로 문서에서 읽은 **OnFileSave** 논리 처럼 작동 합니다는 **ID_FILE_SAVE_AS** 명령 및 새 파일 이름을 제공 하기 위해 사용자에 게 요청 합니다. 가상 함수를 통해 파일을 열고 저장 하는 수행 하는 실제 과정 이루어집니다 `OnSaveDocument`합니다.  
  
     사용자 지정 하는 두 가지 일반적인 이유는 **ID_FILE_SAVE**합니다. 문서 저장 하지 않는 대 한 제거 하면는 **ID_FILE_SAVE** 메뉴 항목 및 사용자 인터페이스에서 도구 모음 단추입니다. 문서에 커밋되지 하지 않음 갖는지도 확인 하십시오 (즉, 절대 호출 하지 `CDocument::SetModifiedFlag`) 및 프레임 워크 문서를 저장할로 인해 발생 하지 것입니다. 디스크 파일을 제외한 임의의 위치를 저장 하는 문서에 대 한 해당 작업에 대 한 새 명령을 정의 합니다.  
  
     경우에 `COleServerDoc`, **ID_FILE_SAVE** 파일 저장 (문서에 대 한 일반) 및 (포함 된 문서)에 대 한 파일 업데이트를 위해 모두 사용 됩니다.  
  
     문서 데이터가 개별 디스크 파일에 저장 되어 있지만 기본값을 사용 하지 않으려는 경우 **CDocument** 구현 직렬화를 재정의 해야 `CDocument::OnSaveDocument` 대신 **OnFileSave**합니다.  
  
-   ID_FILE_SAVE_AS를 다른 파일 이름에서 현재 문서를 저장 합니다.  
  
     **CDocument::OnFileSaveAs** 구현 사용 동일한 **CDocument::DoSave** 도우미 루틴으로 **OnFileSave**합니다. **OnFileSaveAs** 와 마찬가지로 명령을 처리 **ID_FILE_SAVE** 문서에 저장 하기 전에 파일 이름이 없습니다. **COleServerDoc::OnFileSaveAs** 별도 파일로 다른 응용 프로그램에 포함 된 OLE 개체가 나타내는 서버 문서를 저장 하는 논리 일반 문서 데이터 파일을 저장 하려면 구현 합니다.  
  
     논리를 사용자 지정한 경우 **ID_FILE_SAVE**, 사용자 지정 하 고 싶을 것 **ID_FILE_SAVE_AS** "다른 이름으로 저장" 연산이 나와 비슷한 방식으로 적용할 수 없는 문서. 필요 하지 않은 경우 메뉴 모음에서 메뉴 항목을 제거할 수 있습니다.  
  
-   ID_FILE_SAVE_COPY_AS 새 이름 복사 현재 문서를 저장합니다.  
  
     **COleServerDoc::OnFileSaveCopyAs** 구현은와 매우 유사 **CDocument::OnFileSaveAs**제외 하 고 문서 개체가 연결 되지 않은"" 기본 파일에 저장 한 후, 합니다. 즉, 메모리 내 문서 수정 된 경우"" 저장 하기 전에, 여전히 "수정입니다". 또한이 명령은 경로 이름 또는 문서에 저장 되는 제목에는 영향을 주지 않습니다.  
  
-   ID_FILE_UPDATE 포함된 된 문서를 저장 하는 컨테이너를에 알립니다.  
  
     `COleServerDoc::OnUpdateDocument` 구현은 단순히 notifiies 포함 하는 저장 하는 컨테이너입니다. 그런 다음 컨테이너 포함된 개체를 저장 하기 위해 적절 한 OLE Api를 호출 합니다.  
  
-   ID_FILE_PAGE_SETUP 응용 프로그램별 페이지 설정/레이아웃 대화를 호출합니다.  
  
     현재는이 대화 상자에 대 한 어떠한 표준 및 프레임 워크는이 명령의 기본 구현이 없습니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_FILE_PRINT_SETUP 표준 인쇄 설정 대화 상자를 호출 합니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     이 명령은 사용자에 대 한 설정에 인쇄 및 프린터를 사용자 지정할 수 있게 하는 표준 인쇄 설정 대화 상자를 호출 합니다.이 문서 또는 최대에 있는 모든 문서가 응용이 프로그램입니다. 제어판을 사용 하 여 전체 시스템에 대 한 기본 프린터 설정 변경 해야 합니다.  
  
     `CWinApp::OnFilePrintSetup` 만드는 매우 간단한 구현에는 `CPrintDialog` 개체와 호출 된 **CWinApp::DoPrintDialog** 함수 구현 합니다. 이 응용 프로그램 기본 프린터 설정을 설정합니다.  
  
     이 명령은 사용자 지정 하기 위한 일반적인 요구 저장 될 때 문서와 함께 저장 해야 문서별 프린터 설정에 대 한 허용 하는 것입니다. 이 작업을 수행 하려면 메시지 맵 처리기에 추가 해야 프로그램 **CDocument** 를 만드는 클래스는 `CPrintDialog` 개체, 적절 한 프린터 특성으로 초기화 (일반적으로 **hDevMode** 및 **hDevNames**)를 호출 하는 **CPrintDialog::DoModal,** 변경 된 프린터 설정을 저장 합니다. 강력한 구현에 대 한 살펴봐야 구현의 **CWinApp::DoPrintDialog** 오류 검색에 대 한 및 **CWinApp::UpdatePrinterSelection** 실제 기본값을 다루기 위해 및 시스템 차원의 프린터 변경 내용을 추적 합니다.  
  
-   현재 문서의 ID_FILE_PRINT 표준 인쇄  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CView`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     이 명령은 현재 문서를 인쇄 하거나 더를 올바르게 표준 인쇄 대화 상자를 호출 하 고 인쇄 엔진 실행 작업이 포함 된 인쇄 프로세스를 시작 합니다.  
  
     **CView::OnFilePrint** 이 명령과 주 인쇄 루프를 구현 합니다. 가상 호출 `CView::OnPreparePrinting` 인쇄 대화 상자를 사용 하 여 사용자의 프롬프트에 있습니다. 그런 다음 출력 DC는 프린터를 준비 하 고를 인쇄 진행률 대화 상자를 엽니다 (**AFX_IDD_PRINTDLG**), 보냅니다는 `StartDoc` 프린터를 이스케이프 합니다. **CView::OnFilePrint** 도 주 페이지 관련 인쇄 루프를 포함 합니다. 각 페이지에 대 한 가상 호출 `CView::OnPrepareDC` 이어서는 `StartPage` 이스케이프 및 가상 호출 `CView::OnPrint` 해당 페이지에 대 한 합니다. 완료 된 경우, 가상 `CView::OnEndPrinting` 를 호출 하 고 인쇄 진행률 대화 상자를 닫습니다.  
  
     MFC 인쇄 아키텍처는 인쇄 및 인쇄 미리 보기에 대 한 다양 한 방법으로 연결 하도록 설계 되었습니다. 일반적으로 있습니다. 다양 한 `CView` 페이지 관련 인쇄 작업에 대 한 적절 한 재정의 가능 함수입니다. 사용 하 여 프린터 비페이지 지향 출력에서 발견를 교체 하는 응용 프로그램의 경우에는 **ID_FILE_PRINT** 구현 합니다.  
  
-   현재 문서에 대 한 인쇄 미리 보기 모드 ID_FILE_PRINT_PREVIEW 입력 합니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CView`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     **CView::OnFilePrintPreview** 문서화 된 도우미 함수를 호출 하 여 인쇄 미리 보기 모드가 시작 **CView::DoPrintPreview**합니다. **CView::DoPrintPreview** 것과 마찬가지로 인쇄 미리 보기 루프에 대 한 주요 엔진 **OnFilePrint** 인쇄 루프에 대 한 기본 엔진입니다.  
  
     인쇄 미리 보기 작업을 사용자 지정할 수 있습니다는 여러 가지 방법으로 서로 다른 매개 변수를 전달 하 여 **DoPrintPreview**합니다. 참조 하십시오 [기술 참고 30](../mfc/tn030-customizing-printing-and-print-preview.md), 인쇄 미리 보기의 세부 정보 중 일부를 설명 하는 방법 및 사용자 지정 해야 합니다.  
  
-   **ID_FILE_MRU_FILE1**... **FILE16** 파일 MRU에 대 한 명령 Id의 범위 `list`합니다.  
  
     **CWinApp::OnUpdateRecentFileMenu** 의 고급 용도 중 하나는 update 명령 UI 처리기가는 `ON_UPDATE_COMMAND_UI` 메커니즘입니다. 메뉴 리소스 ID 가진 단일 메뉴 항목 정의 필요 하 **ID_FILE_MRU_FILE1**합니다. 해당 메뉴 항목에 처음으로 사용할 수 없는 상태로 유지 됩니다.  
  
     MRU 목록 많아지면, 추가 메뉴 항목이 목록에 추가 됩니다. 표준 `CWinApp` 4 개의 가장 최근에 사용한 파일의 표준 제한을 기본적으로 구현 합니다. 호출 하 여 기본값을 변경할 수 있습니다 `CWinApp::LoadStdProfileSettings` 더 크거나 작은 값을 사용 합니다. MRU 목록 응용 프로그램에 저장 됩니다. INI 파일입니다. 응용 프로그램에서 로드 되는 목록 `InitInstance` 함수를 호출 하면 `LoadStdProfileSettings`, 응용 프로그램이 끝날 때 저장 됩니다. 또한 MRU 명령 업데이트 UI 처리기 파일 메뉴의 표시에 대 한 상대 경로를 절대 경로 변환 합니다.  
  
     **CWinApp::OnOpenRecentFile** 는 `ON_COMMAND` 실제 명령을 수행 하는 처리기. MRU 목록 및 호출에서 파일 이름을 단순히 가져옵니다 `CWinApp::OpenDocumentFile`, 파일을 열어 고 MRU 목록을 업데이트 하는 모든 작업을 수행 하는 합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_EDIT_CLEAR 현재 선택을 해제합니다  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 사용 하 여이 명령을의 구현을 제공 `CEdit::Clear`합니다. 현재 선택 영역이 없는 경우에 명령이 비활성화 됩니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   이 문서 전체를 지웁니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다. MFC 자습서 샘플 [SCRIBBLE](../visual-cpp-samples.md) 예제 구현에 대 한 합니다.  
  
-   ID_EDIT_COPY 현재 선택 영역을 클립보드에 복사 합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 이 명령은 현재 선택한 텍스트를 사용 하 여 CF_TEXT 클립보드에 복사 하는의 구현을 제공 `CEdit::Copy`합니다. 현재 선택 영역이 없는 경우에 명령이 비활성화 됩니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_EDIT_CUT은 클립보드의 현재 선택 항목을 잘라냅니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 사용 하 여 CF_TEXT 클립보드에 현재 선택한 텍스트를 잘라냅니다이 명령의 구현을 제공 `CEdit::Cut`합니다. 현재 선택 영역이 없는 경우에 명령이 비활성화 됩니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   찾기 작업 ID_EDIT_FIND 시작 모덜리스 찾기 대화 상자를 표시 합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 이 명령을 구현 도우미 함수를 호출 하는 구현을 제공 **OnEditFindReplace** 사용 하 고 private 구현 변수에서 이전 찾기/바꾸기 설정을 저장 합니다. `CFindReplaceDialog` 클래스 관리 사용자에 게 확인에 대 한 모덜리스 대화 상자를 사용 합니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_EDIT_PASTE 현재 클립보드 내용을 삽입합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 이 명령을 사용 하 여 선택한 텍스트 바꾸기 현재 클립보드 데이터를 복사 하는 구현을 제공 `CEdit::Paste`합니다. 명령이 비활성화 되어 있는 경우 없습니다 **CF_TEXT** 클립보드에 있습니다.  
  
     **COleClientDoc** 이 명령에 명령 업데이트 UI 처리기를 제공 합니다. 클립보드 포함 가능한 경량 OLE 항목/개체를 포함 하지 않으면 명령이 비활성화 됩니다. 실제 붙여넣기 작업을 수행 하는 실제 명령에 대 한 처리기를 작성 해야 합니다. OLE 응용 프로그램의 다른 형식 붙여 넣을 수도, 경우에 고유한 업데이트 명령 UI 처리기 보기 또는 문서에 제공 해야 (즉, 하기 전에 어딘가에 **COleClientDoc** 명령 대상 라우팅에).  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
     표준 OLE 구현을 대체 하기 위해 사용 하 여 `COleClientItem::CanPaste`합니다.  
  
-   ID_EDIT_PASTE_LINK은 클립보드 내용을 현재에서 링크를 삽입합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `COleDocument` 이 명령에 명령 업데이트 UI 처리기를 제공 됩니다. 클립보드 linkable OLE 항목/개체를 포함 하지 않으면 명령이 비활성화 됩니다. 실제 붙여넣기 작업을 수행 하는 실제 명령에 대 한 처리기를 작성 해야 합니다. OLE 응용 프로그램의 다른 형식 붙여 넣을 수도, 경우에 고유한 업데이트 명령 UI 처리기 보기 또는 문서에 제공 해야 (즉, 하기 전에 어딘가에 `COleDocument` 명령 대상 라우팅에).  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
     표준 OLE 구현을 대체 하기 위해 사용 하 여 `COleClientItem::CanPasteLink`합니다.  
  
-   ID_EDIT_PASTE_SPECIAL은 옵션과 함께 현재 클립보드 내용을 삽입합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다. MFC는이 대화 상자를 제공 하지 않습니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_EDIT_REPEAT 마지막 작업을 반복 합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 이 명령은 마지막 찾기 작업을 반복 하는 구현을 제공 합니다. 마지막 찾기에 대 한 전용 구현 변수가 사용 됩니다. 찾기를 시도할 수 없음 명령이 비활성화 됩니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   바꾸기 작업 ID_EDIT_REPLACE 시작 모덜리스 바꾸기 대화 상자를 표시 합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 이 명령을 구현 도우미 함수를 호출 하는 구현을 제공 **OnEditFindReplace** 사용 하 고 private 구현 변수에서 이전 찾기/바꾸기 설정을 저장 합니다. `CFindReplaceDialog` 클래스는 사용자 요청 하는 모덜리스 대화 상자를 관리 하는 데 사용 됩니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_EDIT_SELECT_ALL 전체 문서를 선택 합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 문서에서 모든 텍스트를 선택 합니다.이 명령의 구현을 제공 합니다. 선택할 수 없는 텍스트가 있는 경우에 명령이 비활성화 됩니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_EDIT_UNDO 마지막 작업 실행 취소합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     `CEditView` 이 구현을 제공 명령을 사용 하 여 `CEdit::Undo`합니다. 명령이 비활성화 되어 있는 경우 `CEdit::CanUndo` FALSE를 반환 합니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_EDIT_REDO 마지막 작업을 다시 실행합니다.  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 각각에 대해 구현 해야 `CView`-클래스를 파생 합니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_WINDOW_NEW 활성 문서에서 다른 창을 시작 합니다.  
  
     **CMDIFrameWnd::OnWindowNew** 현재 문서의 다른 뷰를 포함 하는 다른 프레임을 만들려면 현재 문서의 문서 서식 파일을 사용 하 여이 강력한 기능을 구현 합니다.  
  
     마찬가지로 대부분 여러 문서 MDI (인터페이스) 창 메뉴 명령, 활성 MDI 자식 창이 없습니다 명령이 비활성화 됩니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다. 프레임 창 또는 추가 보기를 만드는 명령을 제공 하려는 경우 것 명령을 직접 한계는 것이 좋습니다. 코드를 복제할 수 **CMDIFrameWnd::OnWindowNew** 을 원하는 대로의 특정 프레임 및 뷰 클래스를 수정 합니다.  
  
-   MDI 창 맨 아래에 ID_WINDOW_ARRANGE 정렬 아이콘  
  
     `CMDIFrameWnd` 도우미 함수 구현에에서이 표준 MDI 명령 구현 **OnMDIWindowCmd**합니다. 이 도우미 명령 Id를 매핑하고 MDI 창 메시지를 따라서 많은 코드를 공유할 수 있습니다.  
  
     마찬가지로 대부분 MDI 창 메뉴 명령, 활성 MDI 자식 창이 없습니다 명령이 비활성화 됩니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_WINDOW_CASCADE 단계적 windows 겹치게 됩니다.  
  
     `CMDIFrameWnd` 도우미 함수 구현에에서이 표준 MDI 명령 구현 **OnMDIWindowCmd**합니다. 이 도우미 명령 Id를 매핑하고 MDI 창 메시지를 따라서 많은 코드를 공유할 수 있습니다.  
  
     마찬가지로 대부분 MDI 창 메뉴 명령, 활성 MDI 자식 창이 없습니다 명령이 비활성화 됩니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_WINDOW_TILE_HORZ 타일 windows 가로로 합니다.  
  
     이 명령은에서 구현 되 `CMDIFrameWnd` 마찬가지로 **ID_WINDOW_CASCADE**다른 MDI Windows 메시지는 작업에 사용 되는 점을 제외 하 고, 합니다.  
  
     응용 프로그램에 대 한 기본 타일 방향을 선택 해야 합니다. 창 "타일" 메뉴 항목에 대 한 ID를 변경 하 여 이렇게 하려면 **ID_WINDOW_TILE_HORZ** 또는 **ID_WINDOW_TILE_VERT**합니다.  
  
-   ID_WINDOW_TILE_VERT 타일 windows 세로로 합니다.  
  
     이 명령은에서 구현 되 `CMDIFrameWnd` 마찬가지로 **ID_WINDOW_CASCADE**다른 MDI Windows 메시지는 작업에 사용 되는 점을 제외 하 고, 합니다.  
  
     응용 프로그램에 대 한 기본 타일 방향을 선택 해야 합니다. 창 "타일" 메뉴 항목에 대 한 ID를 변경 하 여 이렇게 하려면 **ID_WINDOW_TILE_HORZ** 또는 **ID_WINDOW_TILE_VERT**합니다.  
  
-   분할자를 ID_WINDOW_SPLIT 키보드 인터페이스입니다.  
  
     `CView` 에 대해이 명령을 처리 하는 `CSplitterWnd` 구현 합니다. 이 명령은 구현 함수에 위임 합니다 보기 분할자 창의 일부 이면 `CSplitterWnd::DoKeyboardSplit`합니다. 이 분할자 키보드 사용자가을 분할 하거나 창에 분리 해제할 수 있는 모드를 배치 합니다.  
  
     이 명령은 보기 분할자에 없는 경우 비활성화 됩니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_APP_ABOUT 정보 대화 상자를 호출합니다.  
  
     응용 프로그램에 대 한 상자에 대 한 표준 구현은 없습니다. 기본 응용 프로그램 마법사가 만든 응용 프로그램은 응용 프로그램에 대 한 사용자 지정 대화 상자 클래스 만들고 사용자에 대 한 상자로 사용 합니다. 응용 프로그램 마법사에서이 명령을 처리 하 고 대화 상자를 호출 하는 간단한 명령 처리기를 작성할 수도 됩니다.  
  
     이 명령은 거의 항상 구현 합니다.  
  
-   ID_APP_EXIT 응용 프로그램을 종료 합니다.  
  
     **CWinApp::OnAppExit** 전송 하 여이 명령을 처리는 `WM_CLOSE` 응용 프로그램의 주 창에 메시지입니다. 표준 (물을 더티 파일 등)는 응용 프로그램의 종료를 처리는 `CFrameWnd` 구현 합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다. 재정의 `CWinApp::SaveAllModified` 또는 `CFrameWnd` 닫기 논리는 것이 좋습니다.  
  
     이 명령을 구현 하기로 선택한 경우이 명령 ID를 사용 하는 것이 좋습니다.  
  
-   ID_HELP_INDEX 나열 도움말 항목 HLP 파일입니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     `CWinApp::OnHelpIndex` 이 명령은 다르거나 일반적으로 호출 하 여 처리 `CWinApp::WinHelp`합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   도움말을 사용 하는 방법에 도움말 ID_HELP_USING 표시 합니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     `CWinApp::OnHelpUsing` 이 명령은 다르거나 일반적으로 호출 하 여 처리 `CWinApp::WinHelp`합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_CONTEXT_HELP 입력 SHIFT F1 도움말 모드입니다.  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     `CWinApp::OnContextHelp` 도움말 모드 커서 설정, 모달 루프를 입력 하 고, 대기 사용자 도움말을 보려면 기간을 선택 하 여이 명령을 처리 합니다. 참조 하십시오 [기술 참고 28](../mfc/tn028-context-sensitive-help-support.md) MFC 도움말 구현에 대 한 자세한 내용은 합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   현재 컨텍스트에서 ID_HELP 제공 도움말  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     `CWinApp::OnHelp` 현재 응용 프로그램 컨텍스트에 대 한 올바른 도움말 컨텍스트를 가져와서이 명령을 처리 합니다. 이 핸들은 간단한 F1 도움말 처리에 메시지 상자에서 등 수 있습니다. 참조 하십시오 [기술 참고 28](../mfc/tn028-context-sensitive-help-support.md) MFC에 대 한 자세한 내용을 보려면 도움말 구현 합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   컨텍스트에 대 한 기본 도움말을 ID_DEFAULT_HELP 표시  
  
    > [!NOTE]
    >  이를 연결 해야 하면 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.  
  
     이 명령은에 일반적으로 매핑된 `CWinApp::OnHelpIndex`합니다.  
  
     기본 도움말 도움말 색인 간 구분을 원하는 경우 다른 명령 처리기를 제공할 수 있습니다.  
  
-   ID_NEXT_PANE 다음 창으로 이동  
  
     `CView` 에 대해이 명령을 처리 하는 `CSplitterWnd` 구현 합니다. 이 명령은 구현 함수에 위임 합니다 보기 분할자 창의 일부 이면 **CSplitterWnd::OnNextPaneCmd**합니다. 현재 보기 분할자의 다음 창으로 이동 됩니다.  
  
     이 명령은 보기에 분할자 없거나 없는 다음 창으로 이동 하는 경우 비활성화 됩니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_PREV_PANE 이전 창으로 이동  
  
     `CView` 에 대해이 명령을 처리 하는 `CSplitterWnd` 구현 합니다. 이 명령은 구현 함수에 위임 합니다 보기 분할자 창의 일부 이면 **CSplitterWnd::OnNextPaneCmd**합니다. 현재 보기 분할자의 이전 창으로 이동 됩니다.  
  
     이 명령은 보기에 분할자 없거나 없는 이전 창으로 이동 하는 경우 비활성화 됩니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_OLE_INSERT_NEW 새로운 OLE 개체 삽입  
  
     현재이이 명령에 대 한 표준 구현이 없습니다. 에 대해이 구현 해야 프로그램 `CView`-현재 선택 영역에 새 OLE 항목/개체를 삽입 하는 클래스를 파생 합니다.  
  
     모든 OLE 클라이언트 응용 프로그램에는이 명령을 구현 해야 합니다. 응용 프로그램 마법사를 사용 하 여 OLE 옵션 됩니다 만들의 기본 구현을 **OnInsertObject** 를 완료 해야 하는 뷰 클래스에 있습니다.  
  
     MFC OLE 샘플 [OCLIENT](../visual-cpp-samples.md) 이 명령의 전체 구현에 대 한 예제입니다.  
  
-   ID_OLE_EDIT_LINKS 편집 OLE 링크  
  
     `COleDocument` MFC에서 제공 구현의 표준 OLE 연결 대화 상자를 사용 하 여이 명령을 처리 합니다. 이 대화의 구현을 통해 액세스 되는 `COleLinksDialog` 클래스입니다. 현재 문서에 대 한 연결 찾을 수 없는 경우 명령은 사용할 수 없습니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   ID_OLE_VERB_FIRST 중... OLE 동사에 대 한 마지막 ID 범위  
  
     `COleDocument` 이 명령은 ID 범위를 사용 하 여 현재 선택 된 OLE 항목/개체에서 지 원하는 동사에 대 한 합니다. 지정된 된 OLE 항목/개체 형식을 0 개 이상의 사용자 지정 동사를 지원할 수 있으므로이 범위 여야 합니다. 응용 프로그램의 메뉴에서 메뉴 항목의 ID 하나 있어야 **ID_OLE_VERB_FIRST**합니다. 프로그램이 실행 될 때 메뉴 적절 한 메뉴 동사 설명 (또는 많은 동사와 함께 팝업 메뉴)으로 업데이트 됩니다. OLE 메뉴의 관리는에서 처리 `AfxOleSetEditMenu`,이 명령에 대 한 업데이트 명령 UI 처리기에서 취소 합니다.  
  
     이 범위에 있는 명령 ID는 처리에 대 한 명시적인 명령 처리기가 없는 있습니다. **COleDocument::OnCmdMsg** 트래핑이 범위에 모든 명령 Id를 0부터 시작 하는 동사 숫자로 바꿀 고 해당 동사에 대 한 서버를 실행 하기 위해 재정의 됩니다 (사용 하 여 `COleClientItem::DoVerb`).  
  
     사용자 지정 또는 기타 사용이 명령 ID 범위 권장 되지 않습니다.  
  
-   ID_VIEW_TOOLBAR 켜고 도구 모음 설정/해제  
  
     `CFrameWnd` 이 명령 및 명령 업데이트 UI 처리기의 도구 모음 표시 상태를 설정/해제를 처리 합니다. 도구 모음에서 자식 창 id의 프레임의 자식 창 이어야 합니다 `AFX_IDW_TOOLBAR`합니다. 명령 처리기에는 실제로 도구 모음 창의 표시 유형을 전환합니다. `CFrameWnd::RecalcLayout` 새 상태에서 프레임 창 도구 모음을 다시 그리게 사용 됩니다. 도구 모음 표시 되 면 명령 업데이트 UI 처리기 메뉴 항목을 확인 합니다.  
  
     이 명령 처리기를 사용자 지정 권장 되지 않습니다. 추가 도구 모음을 추가 하려는 경우를 복제 하 고 명령 처리기 및이 명령에 명령 업데이트 UI 처리기를 수정 합니다.  
  
-   ID_VIEW_STATUS_BAR 켜고 상태 표시줄 설정/해제  
  
     이 명령은에서 구현 되 `CFrameWnd` 마찬가지로 **ID_VIEW_TOOLBAR**, 다른 자식 창 ID를 제외 하 고 (**AFX_IDW_STATUS_BAR**) 사용 됩니다.  
  
## <a name="update-only-command-handlers"></a>업데이트 전용 명령 처리기  
 여러 표준 명령 Id는 상태 표시줄에서 표시기로 사용 됩니다. 이러한 사용 동일한 처리 메커니즘 명령 업데이트 UI 응용 프로그램 유휴 시간 동안 현재 시각적 상태로 표시 됩니다. 이후 사용자가 선택할 수 없습니다 (즉, 밀어넣을 수 없습니다 상태 표시줄 창), 올 수 없습니다는 `ON_COMMAND` 이러한 명령 Id에 대 한 처리기입니다.  
  
-   **ID_INDICATOR_CAPS** : CAP 잠금 표시기입니다.  
  
-   **ID_INDICATOR_NUM** : NUM lock 표시기입니다.  
  
-   **ID_INDICATOR_SCRL** : SCRL 잠금 표시기입니다.  
  
-   **ID_INDICATOR_KANA** :가 나 잠금 표시기 (일본어 시스템에만 해당).  
  
 이러한 세 가지 모두에서 구현 되는 **CFrameWnd::OnUpdateKeyIndicator**, 적절 한 가상 키에 매핑할 명령 ID를 사용 하는 구현 도우미입니다. 일반적인 구현 사용 하거나 사용 하지 않도록 설정 (비활성화 상태 창에 대 한 텍스트 없음 =)는 `CCmdUI` 적절 한 가상 키 현재 고정 되어 있는지 여부에 따라 개체입니다.  
  
 이 명령 처리기를 사용자 지정 권장 되지 않습니다.  
  
-   **ID_INDICATOR_EXT: EXT**선택 표시기를 종료 합니다.  
  
-   **ID_INDICATOR_OVR: 내용은**e**R**strike 표시기입니다.  
  
-   **ID_INDICATOR_REC: REC**ording 표시기입니다.  
  
 현재이 이러한 지표에 대 한 표준 구현이 없습니다.  
  
 이러한 표시기를 구현 하려는 경우 이러한 표시기 Id 및 상태 표시줄에 표시 되는 표시기의 순서를 유지 관리를 사용 하는 것이 좋습니다 (즉,이 순서 대로: EXT, CAP, NUM, SCRL, 겹침, REC).  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

