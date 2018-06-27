---
title: '연습: MFC 자유 곡선 응용 프로그램 (파트 1) 업데이트 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfe91812d178618b1707f99aa10d6bd492109069
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956797"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>연습: MFC 자유 곡선 응용 프로그램 (파트 1) 업데이트
이 연습에서는 리본 메뉴 사용자 인터페이스를 사용하여 기존 MFC 응용 프로그램을 수정하는 방법을 보여 줍니다. Visual Studio는 Office 2007 리본과 Windows 7 Scenic 리본을 지원합니다. 리본 사용자 인터페이스에 대 한 자세한 내용은 참조 [리본](http://go.microsoft.com/fwlink/p/?linkid=129233) MSDN 웹 사이트에 있습니다.  
  
 이 연습에서는 마우스를 사용하여 줄 그리기를 만들 수 있는 클래식 Scribble 1.0 MFC 샘플을 수정합니다. 이 연습 부분에서는 리본 표시줄에 표시되도록 Scribble 샘플을 수정하는 방법을 보여 줍니다. [2 부](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) 리본 표시줄에 더 많은 단추를 추가 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 [Visual C++ 샘플](../visual-cpp-samples.md)  
  
 [Visual C++ 샘플](../visual-cpp-samples.md)  
  
##  <a name="top"></a> 섹션  
 이 연습 부분에는 다음 단원이 있습니다.  
  
- [기본 클래스 대체](#replaceclass)  
  
- [프로젝트에 비트맵 추가](#addbitmap)  
  
- [프로젝트에 리본 리소스 추가](#addribbon)  
  
- [리본 표시줄의 인스턴스 만들기](#createinstance)  
  
- [리본 범주 추가](#addcategory)  
  
- [응용 프로그램의 모양 설정](#setlook)  
  
##  <a name="replaceclass"></a> 기본 클래스 대체  
 메뉴를 지원하는 응용 프로그램을 리본을 지원하는 응용 프로그램으로 변환하려면 업데이트된 기본 클래스에서 응용 프로그램 프레임 창 및 도구 모음 클래스를 파생시켜야 합니다. 원래 Scribble 샘플을 수정하지 마십시오. 대신 Scribble 프로젝트를 정리하고, 다른 디렉터리에 복사한 다음 복사본을 수정하십시오.  
  
#### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Scribble 응용 프로그램에서 기본 클래스를 대체하려면  
  
1.  Scribble.cpp, 확인 `CScribbleApp::InitInstance` 한 호출을 포함 [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)합니다.  
  
2.  stdafx.h 파일에 다음 코드를 추가합니다.  
  
 ```  
    #include <afxcontrolbars.h>  
 ```  
  
3.  Scribble.h, 수정에 대 한 정의 `CScribbleApp` 클래스에서 파생 된 [CWinAppEx 클래스](../mfc/reference/cwinappex-class.md)합니다.  
  
 ```  
    class CScribbleApp: public CWinAppEx  
 ```  
  
4.  Windows 응용 프로그램이 사용자 기본 설정 데이터를 저장하기 위해 초기화(.ini) 파일을 사용한 경우 Scribble 1.0이 작성됩니다. 초기화 파일 대신 Scribble을 수정하여 레지스트리에 사용자 기본 설정을 저장합니다. 레지스트리 키와 기본 설정을 설정하려면 `CScribbleApp::InitInstance` 문 뒤의 `LoadStdProfileSettings()`에서 다음 코드를 입력합니다.  
  
 ```  
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));

 SetRegistryBase(_T("Settings"));

 ```  
  
5.  MDI(다중 문서 인터페이스) 응용 프로그램에 대한 주 프레임은 더 이상 `CMDIFrameWnd` 클래스로부터 파생되지 않습니다. 대신,에서 파생 되는 [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) 클래스입니다.  
  
     mainfrm.h 및 mainfrm.cpp 파일에서 `CMDIFrameWnd`의 모든 참조를 `CMDIFrameWndEx`로 대체합니다.  
  
6.  childfrm.h 및 childfrm.cpp 파일에서 `CMDIChildWnd`를 `CMDIChildWndEx`로 대체합니다.  
  
     Childfrm에. h 파일 바꾸기 `CSplitterWnd` 와 `CSplitterWndEx`합니다.  
  
7.  새 MFC 클래스를 사용하여 도구 모음 및 상태 표시줄을 수정합니다.  
  
     mainfrm.h 파일에서  
  
    1.  `CToolBar`을 `CMFCToolBar`로 바꿉니다.  
  
    2.  `CStatusBar`을 `CMFCStatusBar`로 바꿉니다.  
  
8.  mainfrm.cpp 파일에서  
  
    1.  `m_wndToolBar.SetBarStyle`를 `m_wndToolBar.SetPaneStyle`으로 대체합니다.  
  
    2.  `m_wndToolBar.GetBarStyle`를 `m_wndToolBar.GetPaneStyle`으로 대체합니다.  
  
    3.  `DockControlBar(&m_wndToolBar)`를 `DockPane(&m_wndToolBar)`으로 대체합니다.  
  
9. ipframe.cpp 파일에서 코드의 다음 세 줄을 주석으로 처리합니다.  
  
 ```  
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);

 pWndFrame->EnableDocking(CBRS_ALIGN_ANY);

    pWndFrame->DockPane(&m_wndToolBar);

 ```  
  
10. 응용 프로그램에 정적으로 연결하려는 경우 프로젝트 리소스(.rc) 파일의 시작 부분에 다음 코드를 추가합니다.  
  
 ```  
    #include "afxribbon.rc"  
 ```  
  
     afxribbon.rc 파일에는 런타임에 필요한 리소스가 포함되어 있습니다. [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md) 응용 프로그램을 만들 때이 파일을 자동으로 포함 합니다.  
  
11. 변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다.  
  
 [[섹션](#top)]  
  
##  <a name="addbitmap"></a> 프로젝트에 비트맵 추가  
 이 연습의 다음 네 개의 단계에서는 비트맵 리소스가 필요합니다. 다양한 방법으로 적절한 비트맵을 얻을 수 있습니다.  
  
-   사용 하 여는 [리소스 편집기](../windows/resource-editors.md) 사용자 고유의 비트맵 고안 하 고 있습니다. 또는 리소스 편집기를 사용하여 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 포함된 이동식 네트워크 그래픽(.png) 이미지에서 비트맵을 어셈블합니다. 이러한 이미지는는 `VS2008ImageLibrary` 디렉터리입니다.  
  
     그러나 리본 사용자 인터페이스에는 특정 비트맵 지원 투명 이미지가 필요합니다. 32 비트 픽셀을 여기서 24 비트 색의 빨강, 녹색 및 파랑 구성 요소를 지정 하 고 8 비트 정의 사용 하 여 투명 한 비트맵은 *알파 채널* 색상의 투명도 지정 하는 합니다. 현재 리소스 편집기에서는 볼 수는 있지만 32비트 픽셀로 비트맵을 수정할 수 없습니다. 따라서, 리소스 편집기 대신에 외부 이미지 편집기를 사용하여 투명한 비트맵을 조작합니다.  
  
-   프로젝트의 다른 응용 프로그램에서 적절한 리소스 파일을 복사한 다음 해당 파일에서 비트맵을 가져옵니다.  
  
 이 연습에서는 샘플 디렉터리에 있는 응용 프로그램에서 리소스 파일을 복사합니다.  
  
#### <a name="to-add-bitmaps-to-the-project"></a>프로젝트에 비트맵을 추가하려면  
  
1.  파일 탐색기를 사용하여 RibbonGadgets 샘플의 리소스 디렉터리(`res`)에서 다음 .bmp 파일을 복사합니다.  
  
    1.  Scribble 프로젝트에 main.bmp를 복사합니다.  
  
    2.  Scribble 프로젝트에 filesmall.bmp 및 filelarge.bmp를 복사합니다.  
  
    3.  filelarge.bmp 및 filesmall.bmp 파일의 새 복사본을 만들 수 있지만 RibbonGadgets 샘플에 해당 복사본을 저장합니다. 해당 복사본의 이름을 homesmall.bmp 및 homelarge.bmp로 바꾼 다음 Scribble 프로젝트로 복사본을 이동합니다.  
  
    4.  toolbar.bmp 파일의 복사본을 만들 수 있지만 RibbonGadgets 샘플에 복사본을 저장합니다. 복사본의 이름을 panelicons.bmp로 바꾼 다음 Scribble 프로젝트로 복사본을 이동합니다.  
  
2.  MFC 응용 프로그램에 대한 비트맵을 가져옵니다. **리소스 뷰**, 두 번 클릭는 **scribble.rc** 노드를 두 번 클릭은 **비트맵** 노드를 차례로 클릭 한 다음 **리소스 추가**합니다. 표시 되는 대화 상자에서 클릭 **가져오기**합니다. 찾아는 `res` 디렉터리를 찾고 main.bmp 파일을 선택한 다음 **열려**합니다.  
  
     main.bmp 비트맵에는 26x26 이미지가 포함됩니다. 비트맵의 ID를 IDB_RIBBON_MAIN으로 변경합니다.  
  
3.  응용 프로그램 단추에 첨부된 파일 메뉴에 대한 비트맵을 가져옵니다.  
  
    1.  10개의 16x16(16x160)이 포함된 filesmall.bmp 파일을 가져옵니다. 만 8 개의 16x16 이미지 (16x128)을 필요 하므로 사용 하 여는 **리소스 뷰** 를 160에서 128로 해당 비트맵의 너비를 변경 합니다. 비트맵의 ID를 IDB_RIBBON_FILESMALL로 변경합니다.  
  
    2.  8개의 32X32(32x256) 이미지가 포함된 filelarge.bmp를 가져옵니다. 비트맵의 ID를 IDB_RIBBON_FILELARGE로 변경합니다.  
  
4.  리본 범주와 패널에 대한 비트맵을 가져옵니다. 리본 표시줄의 각 탭은 범주이며 텍스트 레이블 및 선택적 이미지로 구성되어 있습니다.  
  
    1.  작은 단추 비트맵에 대한 8개의 16x16 이미지가 포함된 homesmall.bmp 비트맵을 가져옵니다. 비트맵의 ID를 IDB_RIBBON_HOMESMALL로 변경합니다.  
  
    2.  큰 단추 비트맵에 대한 8개의 32X32 이미지가 포함된 homelarge.bmp 비트맵을 가져옵니다. 비트맵의 ID를 IDB_RIBBON_HOMELARGE로 변경합니다.  
  
5.  크기가 조정된 리본 패널의 비트맵을 가져옵니다. 전체 창을 표시하기에 리본이 너무 작다면 크기 조정 작업 후에 이러한 비트맵 또는 패널 아이콘이 사용됩니다.  
  
    1.  8개의 16x16 이미지가 포함된 panelicons.bmp 비트맵을 가져옵니다. 에 **속성** 의 창은 **비트맵 편집기**를 64 (16x64)로 비트맵의 너비를 조정 합니다. 비트맵의 ID를 IDB_PANEL_ICONS로 변경합니다.  
  
 [[섹션](#top)]  
  
##  <a name="addribbon"></a> 프로젝트에 리본 리소스 추가  
 메뉴를 사용하는 응용 프로그램을 리본을 사용하는 응용 프로그램으로 변환하는 경우 기존 메뉴를 제거하거나 사용 안 함으로 설정할 필요가 없습니다. 대신 리본 리소스를 만들고, 리본 단추를 추가한 다음 새 단추를 기존 메뉴 항목에 연결합니다. 메뉴를 더 이상 볼 수 없지만 리본 표시줄에서 메시지는 메뉴를 통해 라우팅됩니다. 또한 메뉴 바로 가기는 계속 작동합니다.  
  
 리본은 리본의 왼쪽 위의 큰 단추인 응용 프로그램 단추와 하나 이상의 범주 탭으로 구성됩니다. 각 범주 탭에는 리본 단추 및 컨트롤에 대한 컨테이너 역할을 하는 패널이 하나 이상 포함되어 있습니다. 다음 절차에서는 리본 리소스를 만든 다음 응용 프로그램 단추를 사용자 지정하는 방법을 보여 줍니다.  
  
#### <a name="to-add-a-ribbon-resource-to-the-project"></a>프로젝트에 리본 리소스를 추가하려면  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 **리소스 추가**합니다.  
  
2.  에 **리소스 추가** 대화 상자에서 **리본** 클릭 하 고 **새로**합니다.  
  
     Visual Studio에서는 리본 리소스를 만들어 디자인 뷰에서 엽니다. 리본 리소스 ID는 IDR_RIBBON1에 표시 되는 **리소스 뷰**합니다. 리본에는 범주 하나와 패널 하나가 포함되어 있습니다.  
  
3.  해당 속성을 수정하여 응용 프로그램 단추를 사용자 지정할 수 있습니다. 이 코드에 사용되는 메시지 ID는 Scribble 1.0에 대한 메뉴에 이미 정의되어 있습니다.  
  
4.  디자인 뷰에서 해당 속성을 표시하려면 응용 프로그램 단추를 클릭합니다. 속성 값을 다음과 같이 변경: **이미지** 를 *idb_ribbon_main으로*, **프롬프트** 를 *파일*, **키** *f*, **큰 이미지** 를 *IDB_RIBBON_FILELARGE*, 및 **작은 이미지** 를 *IDB_RIBBON_ FILESMALL*합니다.  
  
5.  다음과 같이 수정하면 사용자가 응용 프로그램 단추를 클릭할 때 나타나는 메뉴가 만들어집니다. 줄임표를 클릭 (**...** ) 옆에 **주 항목** 열려는 **항목 편집기**합니다.  
  
    1.  클릭 **추가** 단추를 추가 합니다. 변경 **캡션** 를 *새 &*, **ID** 를 *ID_FILE_NEW*, **이미지** 를 *0*, **큰 이미지** 를 *0*합니다.  
  
    2.  클릭 **추가** 두 번째 단추를 추가 합니다. 변경 **캡션** 를 *& 저장*, **ID** 를 *ID_FILE_SAVE*, **이미지** 를 *2* , 및 **큰 이미지** 를 *2*합니다.  
  
    3.  클릭 **추가** 세 번째 단추를 추가 합니다. 변경 **캡션** 를 *저장 및 마찬가지로*, **ID** 를 *ID_FILE_SAVE_AS*, **이미지** 를*3*, 및 **큰 이미지** 를 *3*합니다.  
  
    4.  클릭 **추가** 네 번째 단추를 추가 합니다. 변경 **캡션** 를 *인쇄 &*, **ID** 를 *ID_FILE_PRINT*, **이미지** 를 *4* , 및 **큰 이미지** 를 *4*합니다.  
  
    5.  변경의 **항목** 형식을 **구분 기호** 클릭 하 고 **추가**합니다.  
  
    6.  변경 된 **항목** 형식을 **단추**합니다. 클릭 **추가** 다섯 번째 단추를 추가 합니다. 변경 **캡션** 를 *닫기 &*, **ID** 를 *ID_FILE_CLOSE*, **이미지** 를 *5* , 및 **큰 이미지** 를 *5*합니다.  
  
6.  다음과 같이 수정하면 이전 단계에서 만든 인쇄 단추 아래에 하위 메뉴가 만들어집니다.  
  
    1.  클릭는 **인쇄** 단추, 변경는 **항목** 형식을 **레이블**, 클릭 하 고 **삽입**합니다. 변경 **캡션** 를 *미리 보기와 문서 인쇄*합니다.  
  
    2.  클릭는 **인쇄** 단추, 변경의 **항목** 형식을 **단추**, 클릭 하 고 **삽입**합니다. 변경 **캡션** 를 *인쇄 &*, **ID** 를 *ID_FILE_PRINT*, **이미지** 를 *4* , 및 **큰 이미지** 를 *4*합니다.  
  
    3.  클릭는 **인쇄** 단추를 선택한 다음 클릭 **삽입** 단추를 추가 합니다. 변경 **캡션** 를 *& 빠른 인쇄*, **ID** 를 *ID_FILE_PRINT_DIRECT*, **이미지** 를*7*, 및 **큰 이미지** 를 *7*합니다.  
  
    4.  클릭는 **인쇄** 단추를 선택한 다음 클릭 **삽입** 다른 단추를 추가 합니다. 변경 **캡션** 를 *인쇄 & 보기*, **ID** 를 *ID_FILE_PRINT_PREVIEW*, **이미지** 를 *6*, 및 **큰 이미지** 를 *6*합니다.  
  
    5.  이제 수정한는 **주 항목**합니다. 클릭 **닫기** 종료 하 고 **항목 편집기**합니다.  
  
7.  다음과 같이 수정하면 응용 프로그램 단추 메뉴의 아래쪽에 나타나는 종료 단추가 만들어집니다.  
  
    1.  에 **속성** 창에서 줄임표를 클릭 (**...** ) 옆에 **단추** 열려는 **항목 편집기**합니다.  
  
    2.  클릭 **추가** 단추를 추가 합니다. 변경 **캡션** 를 *끝낸*, **ID** 를 *ID_APP_EXIT*, **이미지** 를 *8* .  
  
 [[섹션](#top)]  
  
##  <a name="createinstance"></a> 리본 표시줄의 인스턴스 만들기  
 다음 단계에서는 응용 프로그램 시작 시 리본 표시줄의 인스턴스를 만드는 방법을 보여 줍니다. 응용 프로그램에 리본 표시줄을 추가하려면 mainfrm.h 파일에 리본 표시줄을 선언합니다. 그런 다음 mainfrm.cpp 파일에서 리본 리소스를 로드하는 코드를 작성합니다.  
  
#### <a name="to-create-an-instance-of-the-ribbon-bar"></a>리본 표시줄의 인스턴스를 만들려면  
  
1.  mainfrm.h 파일에서 주 프레임에 대한 클래스 정의인 `CMainFrame`의 보호된 섹션에 데이터 멤버를 추가합니다. 이 멤버는 리본 표시줄을 나타냅니다.  
  
 ' ' * / 리본 / 응용 프로그램에 대 한 표시줄  
    CMFCRibbonBar m_wndRibbonBar;  
 ```  
  
2.  In the mainfrm.cpp file, add the following code before the final **return** statement at the end of the `CMainFrame::OnCreate` function. This creates an instance of the ribbon bar.  
  
 ``` *// Create the ribbon bar  
    if (!m_wndRibbonBar.Create(this))  
 {  
    return -1;   //Failed to create ribbon bar  
 }  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
 [[섹션](#top)]  
  
##  <a name="addcategory"></a> 리본 리소스를 사용자 지정  
 응용 프로그램 단추를 만들었으므로 리본에 요소를 추가할 수 있습니다.  
  
> [!NOTE]
>  이 연습에서는 모든 패널에 대해 동일한 패널 아이콘을 사용합니다. 그러나 다른 아이콘을 표시하기 위해 다른 이미지 목록 인덱스를 사용할 수 있습니다.  
  
#### <a name="to-add-a-home-category-and-edit-panel"></a>홈 범주 및 편집 패널을 추가하려면  
  
1.  Scribble 프로그램에서는 하나의 범주만 필요로 합니다. 디자인 뷰에서 클릭 **범주** 해당 속성을 표시 합니다. 속성 값을 다음과 같이 변경: **캡션** 를 *& 홈*, **큰 이미지** 를 *IDB_RIBBON_HOMELARGE*,  **작은 이미지** 를 *IDB_RIBBON_HOMESMALL*합니다.  
  
2.  각 리본 범주는 명명된 패널로 구성되어 있습니다. 각 패널에는 관련 작업을 수행하는 컨트롤 집합이 포함되어 있습니다. 이 범주에는 한 패널이 있습니다. 클릭 **패널**를 바꾼 다음 **캡션** 를 *편집* 및 **이미지 인덱스:** 를 *0*합니다.  
  
3.  에 **편집** 패널에서 문서의 콘텐츠 지우기를 담당 하는 단추를 추가 합니다. 이 단추에 대한 메시지 ID는 IDR_SCRIBBTYPE 메뉴 리소스에서 이미 정의되었습니다. 지정 *모두 지우기* 단추 텍스트 및 단추를 데코레이팅하는 비트맵 인덱스입니다. 열기는 **도구 상자**, 한 다음 끌어는 **단추** 에 **편집** 패널입니다. 단추를 클릭 한 다음 변경 **캡션** 를 *모두 지우기*, **ID** 를 *ID_EDIT_CLEAR_ALL*, **이미지인덱스:** 를 *0*, **큰 이미지 인덱스** 를 *0*합니다.  
  
4.  변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. Scribble 응용 프로그램은 표시되어야 하며 메뉴 모음 대신 창의 위쪽에 리본 표시줄이 있어야 합니다. 리본 표시줄에는 하나의 범주 있어야 **홈**, 및 **홈** 한 패널 있어야 **편집**합니다. 추가한 리본 단추는 기존 이벤트 처리기와 연결할 및 **열려**, **닫기**, **저장**, **인쇄**, 및 **모두 지우기** 단추는 예상 대로 작동 해야 합니다.  
  
 [[섹션](#top)]  
  
##  <a name="setlook"></a> 응용 프로그램의 모양 설정  
 A *비주얼 관리자* 는 응용 프로그램에 대 한 모든 그리기를 제어 하는 전역 개체입니다. 원래 Scribble 응용 프로그램은 Office 2000 UI(사용자 인터페이스) 스타일을 사용하므로 해당 응용 프로그램이 더 이상 사용되지 않는 것처럼 보일 수 있습니다. Office 2007 응용 프로그램과 비슷하도록 Office 2007 비주얼 관리자를 사용하여 응용 프로그램을 다시 설정할 수 있습니다.  
  
#### <a name="to-set-the-look-of-the-application"></a>응용 프로그램의 모양을 설정하려면  
  
1.  `CMainFrame::OnCreate` 함수에서 다음 코드를 입력하여 기본 비주얼 관리자 및 스타일을 변경합니다.  
  
 ' ' * / / Office 2007로 기본 관리자 설정   
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));

 CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);

 ```  
  
2.  Save the changes, and then build and run the application. The application UI should resemble the Office 2007 UI.  
  
 [[Sections](#top)]  
  
## Next Steps  
 You have modified the classic Scribble 1.0 MFC sample to use the Ribbon Designer. Now go to [Part 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)   
 [Walkthrough: Updating the MFC Scribble Application (Part 2)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)

