---
title: "연습: MFC 자유 곡선 응용 프로그램 업데이트(파트 1) | Microsoft Docs"
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
  - "예제[C++], 기존 응용 프로그램 업데이트"
  - "MFC 기능 팩, 기존 응용 프로그램 업데이트"
  - "Office Fluent UI, 포팅"
  - "리본 UI, 포팅"
  - "샘플[C++], 기존 응용 프로그램 업데이트"
  - "연습[C++], 기존 응용 프로그램 업데이트"
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
caps.latest.revision: 54
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 50
---
# 연습: MFC 자유 곡선 응용 프로그램 업데이트(파트 1)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 리본 메뉴 사용자 인터페이스를 사용하여 기존 MFC 응용 프로그램을 수정하는 방법을 보여줍니다.  Visual Studio Office 2007 리본 메뉴와 Windows 7 Scenic 리본 메뉴를 지원합니다.  리본 사용자 인터페이스에 대한 자세한 내용은 MSDN 웹 사이트에서 [리본](http://go.microsoft.com/fwlink/?LinkId=129233)을 참조하십시오.  
  
 이 연습에서는 마우스 줄을 그리는 데 사용할 수 있는 기존의 1.0 Scribble MFC 샘플을 수정합니다.  이 연습 부분에서는 리본 표시줄이 표시되도록 Scribble 샘플을 수정하는 방법을 보여줍니다.  [2부](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) 리본 메뉴 모음에 더 많은 단추를 추가합니다.  
  
## 사전 요구 사항  
 [Visual C\+\+ 샘플](../top/visual-cpp-samples.md)  
  
 [Visual C\+\+ 샘플](../top/visual-cpp-samples.md)  
  
##  <a name="top"></a> 단원  
 이 연습 부분에는 다음 섹션이 있습니다.  
  
-   [기본 클래스 교체](#replaceClass)  
  
-   [비트맵을 프로젝트에 추가합니다.](#addBitmap)  
  
-   [리본 리소스를 프로젝트에 추가합니다.](#addRibbon)  
  
-   [리본 표시줄의 인스턴스를 만듭니다.](#createInstance)  
  
-   [리본 범주를 추가합니다.](#addCategory)  
  
-   [응용프로그램의 모양을 설정합니다.](#setLook)  
  
##  <a name="replaceClass"></a> 기본 클래스 교체  
 리본을 지원하는 응용 프로그램에 메뉴를 지원하는 응용 프로그램을 변환하려면, 업데이트된 기본 클래스로부터 응용 프로그램, 프레임 창 및 도구 클래스를 파생해야 합니다. \(원래 Scribble 샘플을 수정 하지 마십시오 대신 Scribble 프로젝트 정리하고, 다른 디렉터리에 복사한 다음 복사본을 수정하십시오\)  
  
#### Scribble 응용 프로그램에서 기본 클래스의 이름을 바꾸려면  
  
1.  Scribble.cpp에서  `CScribbleApp::InitInstance` 이 [AfxOleInit](../Topic/AfxOleInit.md)의 호출을 포함하는지 확인합니다.  
  
2.  stdafx.h 파일에 다음 코드를 추가합니다.  
  
    ```  
    #include <afxcontrolbars.h>  
    ```  
  
3.  Scribble.h에서, [CWinAppEx Class](../mfc/reference/cwinappex-class.md)로부터 파생되도록  `CScribbleApp` 클래스에 대한 정의를 수정합니다.  
  
    ```  
    class CScribbleApp: public CWinAppEx  
    ```  
  
4.  Windows 응용 프로그램이 사용자 기본 설정 데이터를 저장하기위해 초기화 \(.ini\) 파일을 사용하면 자유 곡선 1.0이 작성됩니다.  초기화 파일 대신, 레지스트리에 사용자 기본 설정을 저장하는 자유를 수정합니다.  레지스트리 키와 기본 설정을 설정하려면,  `LoadStdProfileSettings()`  문 뒤에  `CScribbleApp::InitInstance` 에서 다음 코드를 입력합니다.  
  
    ```  
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));  
    SetRegistryBase(_T("Settings"));  
    ```  
  
5.  다중 문서 인터페이스\(MDI\) 응용 프로그램에 대한 주 프레임은 더 이상  `CMDIFrameWnd`  클래스로부터 파생되지 않습니다.  대신, [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) 을 클래스로부터 파생됩니다.  
  
     Mainfrm.h 및 mainfrm.cpp 파일에서  `CMDIFrameWnd` 의 모든 참조를  `CMDIFrameWndEx` 로 대체합니다.  
  
6.  Childfrm.h 및 childfrm.cpp 파일에서  `CMDIChildWnd` 를  `CMDIChildWndEx` 로 대체합니다.  
  
     childfrm. h 파일에서  `CSplitterWnd` 를  `CSplitterWndEx` 로 대체합니다.  
  
7.  새 MFC 클래스를 사용하여 상태 표시줄 및 도구 모음을 수정합니다.  
  
     mainfrm.h 파일:  
  
    1.  `CToolBar`을 `CMFCToolBar`로 바꿉니다.  
  
    2.  `CStatusBar`을 `CMFCStatusBar`로 바꿉니다.  
  
8.  mainfrm.cpp 파일:  
  
    1.  `m_wndToolBar.SetBarStyle`을 `m_wndToolBar.SetPaneStyle`로 바꿉니다.  
  
    2.  `m_wndToolBar.GetBarStyle`을 `m_wndToolBar.GetPaneStyle`로 바꿉니다.  
  
    3.  `DockControlBar(&m_wndToolBar)`을 `DockPane(&m_wndToolBar)`로 바꿉니다.  
  
9. Ipframe.cpp 파일에서 코드의 다음 세 줄을 주석처리 합니다.  
  
    ```  
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);  
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);  
    pWndFrame->DockPane(&m_wndToolBar);  
    ```  
  
10. 응용 프로그램에 정적으로 연결 하려는 경우, 프로젝트 리소스 \(.rc\) 파일의 시작 부분에 다음 코드를 추가합니다.  
  
    ```  
    #include "afxribbon.rc"  
    ```  
  
     실행 시에 Afxribbon.rc 파일은 필요한 리소스를 포함합니다.  [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)은 응용 프로그램을 만들 때 이 파일을 자동으로 포함합니다.  
  
11. 모든 변경을 저장한 다음 응용 프로그램을 빌드하고 실행합니다.  
  
 \[[단원](#top)\]  
  
##  <a name="addBitmap"></a> 비트맵을 프로젝트에 추가합니다.  
 이 연습의 다음 네 개의 단계에서는 비트맵 리소스를 해야합니다.  다양한 방법으로 적절한 비트맵을 얻을 수 있습니다.  
  
-   [Resource Editors](../mfc/resource-editors.md)를 사용하여 사용자 고유의 비트맵을 고안합니다.  또는 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]가 포함되어 있는 이동식 네트워크 그래픽 \(.png\) 이미지의 비트맵에 리소스 편집기를 사용합니다.  이러한 이미지들은  `VS2008ImageLibrary`  디렉터리에 있습니다.  
  
     그러나, 리본 사용자 인터페이스는 특정 비트맵 투명 이미지를 지원해야 합니다.  투명한 비트맵은 24 비트가 색의 빨강, 녹색 및 파랑 구성 요소를 지정하는 32 비트 픽셀을 사용하고,  8 비트는 색상의 투명도 지정하는 *알파 채널*을 정의합니다.  현재 리소스 편집기에서는 볼 수는 있지만, 32 비트 픽셀 비트맵은 수정할 수 없습니다.  따라서, 투명 한 비트맵을 조작할 수 있는 리소스 편집기 대신에 외부 이미지 편집기를 사용합니다.  
  
-   프로젝트에 다른 응용 프로그램에서 적절한 리소스 파일을 복사하고 해당 파일에서 비트맵을 가져옵니다.  
  
 이 연습에서는 샘플 디렉터리에 있는 응용 프로그램에서 리소스 파일을 복사합니다.  
  
#### 프로젝트에 비트맵을 추가하려면  
  
1.  파일 탐색기를 사용하여 RibbonGadgets 샘플의 리소스 디렉터리\(`res`\)에서 다음.bmp 파일 복사합니다 :  
  
    1.  자유 프로젝트에 main.bmp를 복사합니다.  
  
    2.  Scribble 프로젝트에 Filesmall.bmp 및 filelarge.bmp을 복사합니다.  
  
    3.  Filelarge.bmp 및 filesmall.bmp 파일의 새 복사본을 만들수 있지만, RibbonGadgets 샘플에서 복사본을 저장합니다.  homesmall.bmp 및 homelarge.bmp의 이름을 바꾸고 Scribble 프로젝트 복사본을 이동합니다.  
  
    4.  Toolbar.bmp 파일의 복사본을 만들 수 있지만, RibbonGadgets 샘플에 복사본을 저장합니다.  panelicons.bmp 복사본의 이름을 바꾸고 Scribble 프로젝트 복사본을 이동합니다.  
  
2.  MFC 응용 프로그램에 비트맵을 가져옵니다.  **자원 보기**에서, **scribble.rc** 노드를 더블클릭하고,  **비트맵**노드를 더블클릭하고나서  **리소스 추가**를 클릭합니다.  나타난 대화 상자에서 **가져오기**를 클릭합니다.   `res`  디렉터리를 찾고, main.bmp 파일을 선택한 다음 **열기**를 클릭합니다.  
  
     main.bmp 비트맵 26 x 26 이미지를 포함합니다.  IDB\_RIBBON\_MAIN에는 비트맵의 ID를 변경합니다.  
  
3.  응용 프로그램 단추에 첨부된 파일 메뉴에 대한 비트맵을 가져옵니다.  
  
    1.  10 개의 16 x 16 \(16 x 160\)가 포함 된 filesmall.bmp 파일을 가져옵니다.  8 개의 16 x 16 이미지 \(128 x 16\)가 필요하기 때문에, **리소스 뷰**를 사용하여 128에 160에서 비트맵의 너비를 변경합니다.  IDB\_RIBBON\_FILESMALL에는 비트맵의 ID를 변경합니다.  
  
    2.  8개의 32 X 32 \(32 x 256\)이미지를 포함한 filelarge.bmp을 가져옵니다.  IDB\_RIBBON\_FILELARGE에는 비트맵의 ID를 변경합니다.  
  
4.  리본 범주와 패널에 대한 비트맵을 가져옵니다.  리본 메뉴 모음에 있는 각 탭은 범주, 텍스트 레이블 구성 및 이미지 옵션으로 구성됩니다.  
  
    1.  작은 단추 비트맵에 대한  8개의 16 x 16 이미지 포함된 homesmall.bmp 비트맵을 가져옵니다.  IDB\_RIBBON\_HOMESMALL에는 비트맵의 ID를 변경합니다.  
  
    2.  8개의 32 X 32 이미지 비트맵 단추를 포함하는 homelarge.bmp 비트맵을 가져옵니다.  IDB\_RIBBON\_HOMELARGE에는 비트맵의 ID를 변경합니다.  
  
5.  크기가 조정된 리본 패널의 비트맵을 가져옵니다.  전체 창을 표시 하기에 리본이 너무 작다면,  크기 조정 작업 후에 비트맵 또는 아이콘 패널이 사용됩니다.  
  
    1.  8개의 16 x 16 이미지를 포함하는 panelicons.bmp 비트맵을 가져옵니다.  **비트맵 편집기**의 **속성**창에서 64 \(64 x 16\) 비트맵의 너비를 조정합니다.  IDB\_PANEL\_ICONS에는 비트맵의 ID를 변경합니다.  
  
 \[[단원](#top)\]  
  
##  <a name="addRibbon"></a> 리본 리소스를 프로젝트에 추가합니다.  
 리본 메뉴를 사용한 응용 프로그램 메뉴를 사용하는 응용 프로그램을 변환할 떄, 기존 메뉴를 사용 하지않도록 설정하거나 제거할 필요가 없습니다.  대신, 리본 리소스 리본 단추를 생성한 다음 기존 메뉴 항목을 사용하여 새 단추에 연결합니다.  메뉴를 더 이상 볼 수 없지만, 리본 메뉴 모음에서 메세지는 메뉴를 통해 라우팅됩니다.  또한 메뉴 바로 가기는 계속 작동합니다.  
  
 리본 메뉴는 응용 프로그램 단추로 구성됩니다. 버튼은 리본 메뉴의 왼쪽 상단에 있는 큰 단추이고, 하나 이상의 범주 탭으로 구성 됩니다.  각 범주 탭은 리본 메뉴 단추 및 컨트롤에 대한 컨테이너 역할을 하는 패널을 하나 이상 포함하고 있습니다.  다음 절차에서는 리본 리소스를 만든다음 응용 프로그램 단추를 사용자 지정하는 방법을 보여줍니다.  
  
#### 프로젝트에 리본 리소스를 추가하려면  
  
1.  **프로젝트** 메뉴에서 **리소스 추가**를 클릭합니다.  
  
2.  **리소스 추가**대화 상자에서,  **리본** 을 선택한 다음 **New**을 클릭합니다.  
  
     Visual Studio에서 리소스 리소스를 만들어 디자이너 보기에서 엽니다.  리본 리소스 ID는 **리소스 뷰**에서 표시되는 IDR\_RIBBON1입니다.  리본은 패널 및 범주를 포함합니다.  
  
3.  해당 속성을 수정하여 응용 프로그램 단추를 사용자 지정할 수 있습니다.  이 코드에 사용되는 메시지 Id는 자유 1.0에 대한 메뉴에 이미 정의되어 있습니다.  
  
4.  디자인 보기에서 해당 속성을 표시하려면 응용 프로그램 단추를 클릭합니다.  속성 값을 다음과 같이 변경합니다:  **이미지**  에  `IDB_RIBBON_MAIN`,  **확인**  에  `파일`,  **키**  에  `f`,  **큰 이미지** 에  `IDB_RIBBON_FILELARGE`, 및  **작은 이미지** 에  `IDB_RIBBON_FILESMALL`.  
  
5.  다음과 같은 수정은 응용 프로그램 단추를 클릭할 때 나타나는 메뉴를 만듭니다.  **주 항목**옆에 줄임표 \(**...**\)을 클릭해  **항목 편집기**을 엽니다.  
  
    1.  버튼을 추가하려면 **추가**를 클릭합니다.  **Caption** 에 `&New`, **ID** 에 `ID_FILE_NEW`, **Image** 에 `0`, **Image Large** 에 `0` 로 변경합니다.  
  
    2.  두번째 버튼을 추가하려면 **추가**를 클릭합니다.  **Caption** 에 `&Save`, **ID** 에 `ID_FILE_SAVE`, **Image** 에 `2`, 그리고 **Image Large** 에 `2`로 변경합니다.  
  
    3.  세번쨰 버튼을 추가하려면 **추가**를 클릭합니다.  **Caption** 에 `Save &As`, **ID** 에 `ID_FILE_SAVE_AS`, **Image** 에 `3`, 그리고 **Image Large** 에 `3`로 변경합니다.  
  
    4.  네번째 버튼을 추가하려면 **추가**를 클릭합니다.  **Caption** 에 `&Print`, **ID** 에 `ID_FILE_PRINT`, **Image** 에 `2`, 그리고 **Image Large** 에 `4`로 변경합니다.  
  
    5.  **항목** 형식을 **구분**으로 변경한 다음 **추가**를 클릭합니다.  
  
    6.  **항목**형식을 **단추**로 변경합니다.  다섯번째 단추를 추가하려면 **추가**를 클릭합니다.  **Caption** 에 `Save &Close`, **ID** 에 `ID_FILE_CLOSE`, **Image** 에 `5`, 그리고 **Image Large** 에 `5`로 변경합니다.  
  
6.  다음 하위 메뉴에서 이전 단계에서 만든 인쇄 단추의 서브메뉴를 만듭니다.  
  
    1.  **인쇄** 단추를 클릭하고, **항목**형식을  **레이블**로 변경한 다음 **삽입**을 클릭합니다.  **캡션**을 `미리 보기와 문서인쇄`로 변경합니다.  
  
    2.  **인쇄** 단추를 클릭하고, **항목**형식을  **버튼**으로 변경한 다음 **삽입**을 클릭합니다.  **Caption** 에 `&Print`, **ID** 에 `ID_FILE_PRINT`, **Image** 에 `2`, 그리고 **Image Large** 에 `4`로 변경합니다.  
  
    3.  **인쇄**단추를 누른 다음  **삽입** 을 클릭하여 단추를 추가 합니다.  **캡션** 에  `&빠른 인쇄`,  **ID** 에  `ID_FILE_PRINT_DIRECT`,  **이미지** 에  `7`, 및  **큰 이미지** 에  `7`로 변경합니다.  
  
    4.  **인쇄**단추를 누른 다음  **삽입** 을 클릭하여 또 다른 단추를 추가 합니다.  **Caption** 에 `Print Pre&view`, **ID** 에 `ID_FILE_PRINT_PREVIEW`, **Image** 에 `6`, 그리고 **Image Large** 에`6`으로 변경합니다.  
  
    5.  이제 **주 항목**가 수정되었습니다.  **닫기** 를 클릭해 **항목 편집기**를 종료합니다.  
  
7.  다음 수정은 응용 프로그램 단추 메뉴의 아래쪽에 표시 되는 끝내기 단추를 만듭니다.  
  
    1.  **속성**창에서 **Button** 옆에 있는 줄임표 단추\(**...**\)를 클릭하여 **Items Editor**을 엽니다.  
  
    2.  버튼을 추가하려면 **추가**를 클릭합니다.  **Caption** 에 `E&xit`, **ID** 에 `ID_APP_EXIT`, **Image** 에`8`로 변경합니다.  
  
 \[[단원](#top)\]  
  
##  <a name="createInstance"></a> 리본 표시줄의 인스턴스를 만듭니다.  
 다음 단계에서는 응용 프로그램 시작 시 리본 표시줄의 인스턴스를 만드는 방법을 보여줍니다.  응용 프로그램을에 리본 표시줄을 추가 하려면, mainfrm.h 파일에 리본 표시줄을 선언합니다.  그런 다음, mainfrm.cpp 파일에서 리본 리소스를 로드 하는 코드를 작성합니다.  
  
#### 리본 표시줄의 인스턴스를 만들려면  
  
1.  Mainfrm.h 파일에서 주 프레임에 대한 클래스 정의인  `CMainFrame` 의 보호된 섹션에 데이터 멤버 추가합니다.  이 멤버는 리본 표시줄을 나타냅니다.  
  
    ```  
    // Ribbon bar for the application  
    CMFCRibbonBar  m_wndRibbonBar;  
    ```  
  
2.  Mainfrm.cpp 파일에서  `CMainFrame::OnCreate`  함수 끝  `return`  문 바로전에 다음 코드를 추가합니다.   리본 표시줄의 인스턴스를 만듭니다.  
  
    ```  
    // Create the ribbon bar  
    if (!m_wndRibbonBar.Create(this))  
    {  
    return -1;   //Failed to create ribbon bar  
    }  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
 \[[단원](#top)\]  
  
##  <a name="addCategory"></a> 리본 리소스를 사용자 지정합니다.  
 응용 프로그램 단추를 만들었으므로 이제 리본 요소를 추가할 수 있습니다.  
  
> [!NOTE]
>  이 연습에서는 모든 패널에 대한 동일한 제어판 아이콘을 사용합니다.  그러나, 다른 아이콘을 표시하기 위해 다른 이미지 목록 인덱스를 사용할 수 있습니다.  
  
#### 홈 범주를 추가하고 패널을 편집하려면  
  
1.  자유 프로그램은 하나의 범주만 필요합니다.  디자인 보기에서  **범주**를 클릭해 속성을 표시합니다.  속성 값을 다음과 같이 변경합니다:  **캡션** 에  `&홈`,  **큰 이미지** 에  `IDB_RIBBON_HOMELARGE`,  **작은 이미지** 에  `IDB_RIBBON_HOMESMALL`.  
  
2.  각 리본 범주는 명명된 패널로 구성되어 있습니다.  각 패널은 관련된 작업을 수행하는 컨트롤 집합을 포함합니다.  이 범주는 패널을 가지고 있습니다.  **패널**을 클릭해  **캡션**  에  `편집` 및  **이미지 인덱스**  에  `0`로 변경합니다.  
  
3.  **편집** 패널에서 문서 내용을 지우는 역할을 담당하는 단추를 추가합니다.  이 단추에 대한 메시지 ID는 IDR\_SCRIBBTYPE 메뉴에서 리소스에 이미 정의되었습니다.  단추를 꾸미는 비트맵 인덱스 및 단추 텍스트로 `모두 지우기`를 지정합니다.  **도구 상자**를 연 다음, **편집** 패널에 **단추**를 끌어옵니다.  단추를 클릭한 다음 **캡션**  에  `모두 지우기`,  **ID**  에  `이`,  **이미지 인덱스** 에  `0`,  **큰 이미지 인덱스** 에  `0`로 변경합니다.  
  
4.  모든 변경을 저장한 다음 응용 프로그램을 빌드하고 실행합니다.  Scribble 응용 프로그램은 반드시 표시되어야 하며, 메뉴 모음대신 창의 위쪽에 리본 메뉴 모음을 반드시 가지고 있어야 합니다.  리본 메뉴 모음은 하나의 범주가 있어야합니다. **홈**, 및  **홈** 은 **편집**과 같은 하나의 패널을 가져야합니다.  추가된 리본 단추는 기존 이벤트 처리기를 연결하고, **열기**,  **닫기**,  **저장**,  **인쇄**, 및  **모두 지우기** 단추는 예상대로 작동해야 합니다.  
  
 \[[단원](#top)\]  
  
##  <a name="setLook"></a> 응용프로그램의 모양을 설정합니다.  
 *비주얼 관리자*는 응용 프로그램의 모든 그리기를 제어하는 전역개체입니다.  기존의 Scribble 응용 프로그램은 Office 2000 사용자 인터페이스 \(UI\) 스타일을 사용하므로, 응용 프로그램 구식처럼 보일 수 있습니다.  Office 2007 응용 프로그램과 같이 Office 2007 비주얼 관리자를 사용하여 응용 프로그램을 다시 설정할 수 있습니다.  
  
#### 응용 프로그램의 모양을 설정하려면.  
  
1.  `CMainFrame::OnCreate`  함수에서 기본 비주얼 관리자 및 스타일을 변경하려면 다음 코드를 입력합니다.  
  
    ```  
    // Set the default manager to Office 2007   
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));  
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);  
    ```  
  
2.  모든 변경을 저장한 다음 응용 프로그램을 빌드하고 실행합니다.  응용 프로그램 UI는 Office 2007 UI와 유사합니다.  
  
 \[[단원](#top)\]  
  
## 다음 단계  
 리본 디자이너를 사용하여 기존의 1.0 Scribble MFC 샘플을 수정했습니다.  이제  [파트 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)로 넘어갑니다.  
  
## 참고 항목  
 [연습](../mfc/walkthroughs-mfc.md)   
 [연습: MFC 자유 곡선 응용 프로그램 업데이트\(파트 2\)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)