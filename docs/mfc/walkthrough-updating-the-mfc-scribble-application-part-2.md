---
title: "연습: MFC 자유 곡선 응용 프로그램 (2 부) 업데이트 | Microsoft Docs"
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
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 861e0b1f76fcd441ccf5da8f56d5c5dcb23a2b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>연습: MFC 자유 곡선 응용 프로그램 업데이트(파트 2)
[1 부](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) 자유 곡선 응용 프로그램이 연습을 기본 Office Fluent 리본 메뉴를 추가 하는 방법에 설명 했습니다. 이 부분에는 리본 패널 및 메뉴 및 명령을 대신 사용자가 사용할 수 있는 컨트롤을 추가 하는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 [Visual C++ 샘플](../visual-cpp-samples.md)  
  
##  <a name="top"></a> 섹션  
 이 연습 부분에는 다음 단원이 있습니다.  
  
- [리본 메뉴에 새 패널 추가](#addnewpanel)  
  
- [리본에 도움말 패널 추가](#addhelppanel)  
  
- [리본에 펜 패널 추가](#addpenpanel)  
  
- [색 단추를 리본에 추가](#addcolorbutton)  
  
- [문서 클래스에 색 멤버 추가](#addcolormember)  
  
- [펜을 초기화 하 고 저장 환경](#initpensave)  
  
##  <a name="addnewpanel"></a>리본 메뉴에 새 패널 추가  
 이러한 단계에 추가 하는 방법을 보여 줍니다는 **보기** 도구 모음 및 상태 표시줄의 표시 유형을 제어 하는 확인란이 두 개 포함 된 패널 및는 **창** 세로 방향된 분할 포함 된 패널 생성 및 다중 문서 인터페이스 (mdi 다중) 창 배열을 제어 하는 단추입니다.  
  
#### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>리본 표시줄에 뷰 패널 및 창 패널을 추가 하려면  
  
1.  명명 된 패널을 만드는 `View`, 상태 표시줄 및 도구 모음을 설정/해제 하는 확인란이 두 개 있는 합니다.  
  
    1.  **도구 상자**를 끌어는 **패널** 에 **홈** 범주입니다. 다음 두 개의 끌어 **확인란** 패널에 있습니다.  
  
    2.  해당 속성을 수정 하 여 패널을 클릭 합니다. 변경 **캡션** 를 `View`합니다.  
  
    3.  해당 속성을 수정 하려면 첫 번째 확인란을 클릭 합니다. 변경 **ID** 를 `ID_VIEW_TOOLBAR` 및 **캡션** 를 `Toolbar`합니다.  
  
    4.  해당 속성을 수정 하려면 두 번째 확인란을 클릭 합니다. 변경 **ID** 를 `ID_VIEW_STATUS_BAR` 및 **캡션** 를 `Status Bar`합니다.  
  
2.  명명 된 패널을 만드는 `Window` 있는 분할 단추입니다. 사용자가 분할 단추를 클릭 하면 바로 가기 메뉴에 자유 곡선 응용 프로그램에 이미 정의 된 세 가지 명령이 표시 됩니다.  
  
    1.  **도구 상자**를 끌어는 **패널** 에 **홈** 범주입니다. 다음 끌어는 **단추** 패널에 있습니다.  
  
    2.  해당 속성을 수정 하 여 패널을 클릭 합니다. 변경 **캡션** 를 `Window`합니다.  
  
    3.  단추를 클릭합니다. 변경 **캡션** 를 `Windows`, **키** 를 `w`, **큰 이미지 인덱스** 를 `1`, 및 **분할 모드** `False`합니다. 줄임표를 클릭 한 다음 (**...** ) 옆에 **메뉴 항목** 열려는 **항목 편집기** 대화 상자.  
  
    4.  클릭 **추가** 세 개의 단추를 추가 하려면 3 번입니다.  
  
    5.  첫 번째 단추를 클릭 한 후 변경 **캡션** 를 `New Window`, 및 **ID** 를 `ID_WINDOW_NEW`합니다.  
  
    6.  두 번째 단추를 클릭 한 후 변경 **캡션** 를 `Cascade`, 및 **ID** 를 `ID_WINDOW_CASCADE`합니다.  
  
    7.  세 번째 단추를 클릭 한 후 변경 **캡션** 를 `Tile`, 및 **ID** 를 `ID_WINDOW_TILE_HORZ`합니다.  
  
3.  변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. **보기** 및 **창** 패널을 표시할 수 있습니다. 올바르게 작동 하는지 확인 하려면 단추를 클릭 합니다.  
  
 [[섹션](#top)]  
  
##  <a name="addhelppanel"></a>리본에 도움말 패널 추가  
 명명 된 리본 단추에 자유 곡선 응용 프로그램에 정의 되어 있는 두 개의 메뉴 항목을 할당할 수 이제 **도움말 항목** 및 **에 대 한 자유 곡선**합니다. 라는 새 패널에 단추가 추가 됩니다 **도움말**합니다.  
  
#### <a name="to-add-a-help-panel"></a>도움말 패널을 추가 하려면  
  
1.  **도구 상자**를 끌어는 **패널** 에 **홈** 범주입니다. 다음 두 개의 끌어 **단추** 패널에 있습니다.  
  
2.  해당 속성을 수정 하 여 패널을 클릭 합니다. 변경 **캡션** 를 `Help`합니다.  
  
3.  첫 번째 단추를 클릭 합니다. 변경 **캡션** 를 `Help Topics`, 및 **ID** 를 `ID_HELP_FINDER`합니다.  
  
4.  두 번째 단추를 클릭 합니다. 변경 **캡션** 를 `About Scribble...`, 및 **ID** 를 `ID_APP_ABOUT`합니다.  
  
5.  변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. A **도움말** 두 리본 단추가 포함 된 패널을 표시 합니다.  
  
    > [!IMPORTANT]
    >  클릭는 **도움말 항목** 단추, 자유 곡선 응용 프로그램 이라는 압축된 (.chm) HTML 도움말 파일을 엽니다 *your_project_name*. chm. 따라서 프로젝트 Scribble을 지정 하지 않은 경우 이름을 바꿔야 도움말 파일을 프로젝트 이름 합니다.  
  
 [[섹션](#top)]  
  
##  <a name="addpenpanel"></a>리본에 펜 패널 추가  
 이제 추가 펜의 색 및 두께 제어 하는 단추가 표시할 패널입니다. 이 패널 굵은 /가 펜을 전환 하는 확인란을 포함 합니다. 기능의 구문과 유사 합니다는 **두꺼운 선** 자유 곡선 응용 프로그램에서 메뉴 항목입니다.  
  
 원래 Scribble 응용 프로그램 사용자가 클릭할 때 표시 되는 대화 상자에서 펜 너비를 선택할 수 있습니다. **펜 너비** 메뉴. 리본 표시줄 새 컨트롤에 대 한 충분 한 공간을 사용 하므로 리본 메뉴에서 두 개의 콤보 상자를 사용 하 여 대화 상자를 바꿀 수 있습니다. 씬 펜의 너비를 조정 하는 하나의 콤보 상자 및 콤보 상자 굵게 펜의 너비를 조정 합니다.  
  
#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>펜 패널 및 콤보 상자를 리본에 추가 하려면  
  
1.  **도구 상자**를 끌어는 **패널** 에 **홈** 범주입니다. 다음 끌어는 **확인란** 와 두 개의 **콤보 상자** 패널에 있습니다.  
  
2.  해당 속성을 수정 하 여 패널을 클릭 합니다. 변경 **캡션** 를 `Pen`합니다.  
  
3.  이 확인란을 클릭 합니다. 변경 **캡션** 를 `Use Thick`, 및 **ID** 를 `ID_PEN_THICK_OR_THIN`합니다.  
  
4.  첫 번째 콤보 상자를 클릭 합니다. 변경 **캡션** 를 `Thin Pen`, **ID** 를 `ID_PEN_THIN_WIDTH`, **텍스트** 를 `2`, **형식** 를 `Drop List`, 및 **데이터** 를 `1;2;3;4;5;6;7;8;9;`합니다.  
  
5.  두 번째 콤보 상자를 클릭 합니다. 변경 **캡션** 를 `Thick Pen`, **ID** 를 `ID_PEN_THICK_WIDTH`, **텍스트** 를 `5`, **형식** 를 `Drop List`, 및 **데이터** 를 `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`합니다.  
  
6.  기존 메뉴 항목에는 새 콤보 상자 일치 하지 않습니다. 따라서 모든 펜 옵션에 대 한 메뉴 항목을 만들어야 합니다.  
  
    1.  에 **리소스 뷰** 창 IDR_SCRIBBTYPE 메뉴 리소스를 엽니다.  
  
    2.  클릭 **펜** p 열려는**en** 메뉴. 클릭 **여기에 입력** 유형과 `Thi&n Pen`합니다.  
  
    3.  열려는 방금 입력 한 텍스트를 마우스 오른쪽 단추로 클릭는 **속성** 창 및 속성을 변경 ID `ID_PEN_THIN_WIDTH`합니다.  
  
    4.  모든 펜 메뉴 항목에 대 한 이벤트 처리기도 만들어야 합니다. 마우스 오른쪽 단추로 클릭는 **여 & n 펜** 방금 만든을 클릭 한 다음 메뉴 항목 **이벤트 처리기 추가**합니다. **이벤트 처리기 마법사** 표시 됩니다.  
  
    5.  에 **클래스 목록** 상자 선택 마법사에 **CScribbleDoc** 클릭 하 고 **추가 및 편집**합니다. 라는 이벤트 처리기를 만들고이 `CScribbleDoc::OnPenThinWidth`합니다.  
  
    6.  다음 코드를 `CScribbleDoc::OnPenThinWidth`에 추가합니다.  
  
 ``` *리본 메뉴에 대 한 단서 CMFCRibbonBar 모음* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) GetRibbonBar();-> ASSERT_VALID(pRibbon); */ CMFCRibbonComboBox 씬 너비 콤보 상자에 대 한 포인터를 가져올 /* pThinComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox, pRibbon FindByID(ID_PEN_THIN_WIDTH));-> * //Get 선택한 값  
    int nCurSel = pThinComboBox GetCurSel();-> 경우 (nCurSel > = 0)  
{  
m_nThinWidth atoi = (pThinComboBox GetItem(nCurSel));를->.

 (를) * / / 선택한 너비를 사용 하 여 새 펜 만들기  
    ReplacePen();

 ```  
  
7.  Next, create a menu item and event handlers for the thick pen.  
  
    1.  In the **Resource View** window, open the IDR_SCRIBBTYPE menu resource.  
  
    2.  Click **Pen** to open the pen menu. Then click **Type Here** and type `Thic&k Pen`.  
  
    3.  Right-click the text that you just typed to display the **Properties** window. Change the ID property to `ID_PEN_THICK_WIDTH`.  
  
    4.  Right-click the **Thick Pen** menu item that you just created and then click **Add Event Handler**. The **Event Handler Wizard** is displayed.  
  
    5.  In the **Class list** box of the wizard, select **CScribbleDoc** and then click **Add and Edit**. This creates an event handler named `CScribbleDoc::OnPenThickWidth`.  
  
    6.  Add the following code to `CScribbleDoc::OnPenThickWidth`.  
  
 ``` *// Get a pointer to the ribbon bar  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
    CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
*// Get the selected value  
    int nCurSel = pThickComboBox->GetCurSel();
if (nCurSel>= 0)  
 {  
    m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));

 } *// Create a new pen using the selected width  
    ReplacePen();

 ```  
  
8.  변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. 새 단추와 콤보 상자를 표시 합니다. Scribble 하려면 다른 펜 너비를 사용 하십시오.  
  
 [[섹션](#top)]  
  
##  <a name="addcolorbutton"></a>펜 패널에 색 단추를 추가합니다.  
 다음에 추가 [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) 사용자 수 있는 개체 컬러로 scribble 합니다.  
  
#### <a name="to-add-a-color-button-to-the-pen-panel"></a>펜 패널에 색 단추를 추가 하려면  
  
1.  색 단추를 추가 하기 전에 그에 대 한 메뉴 항목을 만듭니다. 에 **리소스 뷰** 창 IDR_SCRIBBTYPE 메뉴 리소스를 엽니다. 클릭는 **펜** 메뉴 항목 펜 메뉴를 엽니다. 클릭 **여기에 입력** 유형과 `&Color`합니다. 표시 하려면 방금 입력 한 텍스트를 마우스 오른쪽 단추로 클릭는 **속성** 창. ID를 변경 `ID_PEN_COLOR`합니다.  
  
2.  이제 색 단추를 추가 합니다. **도구 상자**를 끌어는 **색 단추** 에 **펜** 패널입니다.  
  
3.  색 단추를 클릭 합니다. 변경 **캡션** 를 `Color`, **ID** 를 `ID_PEN_COLOR`, **SimpleLook** 를 `True`, **큰 이미지 인덱스** 를 `1`, 및 **분할 모드** 를 `False`합니다.  
  
4.  변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. 에 표시 될 새 색 단추는 **펜** 패널입니다. 그러나 이벤트 처리기 없는 때문에 사용할 수 없습니다. 다음 단계에는 색 단추에 대 한 이벤트 처리기를 추가 하는 방법을 보여 줍니다.  
  
 [[섹션](#top)]  
  
##  <a name="addcolormember"></a>문서 클래스에 색 멤버 추가  
 원래 Scribble 응용 프로그램에 컬러 펜이 없기 때문에 구현을 작성 해야 합니다. 펜 색입니다. 문서를 저장 하기 위해 문서 클래스에 새 멤버 추가`CscribbleDoc.`  
  
#### <a name="to-add-a-color-member-to-the-document-class"></a>문서 클래스에 색 구성원을 추가 하려면  
  
1.  Scribdoc.h에는 `CScribbleDoc` 클래스를 찾습니다는 `// Attributes` 섹션. 다음 코드 줄의 정의 뒤에 추가 `m_nThickWidth` 데이터 멤버입니다.  
  
 ' ' * / 현재 펜 색 /  
    COLORREF m_penColor;  
 ```  
  
2.  Every document contains a list of stokes that the user has already drawn. Every stroke is defined by a `CStroke` object. The `CStroke` class does not include information about pen color. Therefore, you must modify the class. In scribdoc.h, in the `CStroke` class, add the following lines of code after the definition of the `m_nPenWidth` data member.  
  
 ``` *// Pen color for the stroke  
    COLORREF m_penColor;  
 ```  
  
3.  Scribdoc.h에서 새 추가 `CStroke` 생성자 매개 변수를 가진 두께 및 색을 지정 합니다. 뒤에 코드의 다음 줄 추가 `CStroke(UINT nPenWidth);` 문.  
  
 ```  
    CStroke(UINT nPenWidth, COLORREF penColor);

 ```  
  
4.  Scribdoc.cpp에서 새 구현을 추가 `CStroke` 생성자입니다. 다음 코드의 구현을 뒤에 추가 `CStroke::CStroke(UINT nPenWidth)` 생성자입니다.  
  
 ' ' * / 문서를 사용 하는 생성자의 현재 / 두께 및 색  
    CStroke::CStroke (UINT nPenWidth, COLORREF penColor)  
 {  
    m_nPenWidth nPenWidth; =  
    m_penColor penColor; =  
    m_rectBounding.SetRectEmpty();

 }  
 ```  
  
5.  Change the second line of the `CStroke::DrawStroke` method as follows.  
  
 ```  
    경우 (! penStroke.CreatePen (PS_SOLID, m_nPenWidth, m_penColor))  
 ```  
  
6.  Set the default pen color for the document class. In scribdoc.cpp, add the following lines to `CScribbleDoc::InitDocument`, after the `m_nThickWidth = 5;` statement.  
  
 ``` *// default pen color is black  
    m_penColor = RGB(0,
    0,
    0);

 ```  
  
7.  Scribdoc.cpp, 변경의 첫 번째 줄은 `CScribbleDoc::NewStroke` 다음과 메서드.  
  
 ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);

 ```  
  
8.  변경의 마지막 줄은 `CScribbleDoc::ReplacePen` 메서드를 다음 합니다.  
  
 ```  
    m_penCur.CreatePen(PS_SOLID,
    m_nPenWidth,
    m_penColor);

 ```  
  
9. 추가한는 `m_penColor` 이전 단계에서 멤버입니다. 이제 색 단추를 설정 하는 멤버에 대 한 이벤트 처리기를 만듭니다.  
  
    1.  에 **리소스 뷰** 창 IDR_SCRIBBTYPE 메뉴 리소스를 엽니다.  
  
    2.  마우스 오른쪽 단추로 클릭는 **색** 메뉴 항목을 클릭 하 여 **이벤트 처리기 추가**합니다. **이벤트 처리기 마법사** 나타납니다.  
  
    3.  에 **클래스 목록** 상자 선택 마법사에 **CScribbleDoc** 클릭 하 고는 **추가 및 편집** 단추입니다. 그렇기 때문에 `CScribbleDoc::OnPenColor` 이벤트 처리기 스텁 합니다.  
  
10. 에 대 한 스텁 교체는 `CScribbleDoc::OnPenColor` 이벤트 처리기를 다음 코드로 합니다.  
  
 ```  
    void CScribbleDoc::OnPenColor()  
 { *// Change pen color to reflect color button's current selection  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
    CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

    m_penColor = pColorBtn->GetColor();
*// Create new pen using the selected color  
    ReplacePen();

 }  
 ```  
  
11. 변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. 색 단추를 누르고 펜의 색을 변경할 수 있어야 합니다.  
  
 [[섹션](#top)]  
  
##  <a name="initpensave"></a>펜을 초기화 하 고 저장 환경  
 다음으로, 색 및 펜의 너비를 초기화 합니다. 마지막으로 저장 하 고 파일에서 그리기 색을 로드 합니다.  
  
#### <a name="to-initialize-controls-on-the-ribbon-bar"></a>리본 표시줄에 컨트롤을 초기화  
  
1.  리본 표시줄의 펜을 초기화 합니다.  
  
     scribdoc.cpp에 다음 코드를 추가 `CScribbleDoc::InitDocument` 메서드 이후에 `m_sizeDoc = CSize(200,200)` 문.  
  
 ```*/ UI 리본 CMFCRibbonBar 해당 초기 값으로 다시 설정 /* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) GetRibbonBar();-> ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton pColorBtn = DYNAMIC_DOWNCAST (CMFCRibbonColorButton, pRibbon-> FindByID(ID_PEN_COLOR)); * / 설정 / 검정색으로 ColorButton  
    pColorBtn SetColor RGB ((0, 0, 0));->

 CMFCRibbonComboBox pThinComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox, pRibbon-> FindByID(ID_PEN_THIN_WIDTH)); * / 설정 / 2 씬 펜 콤보 상자  
    pThinComboBox SelectItem(1);->

 CMFCRibbonComboBox pThickComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox, pRibbon-> FindByID(ID_PEN_THICK_WIDTH)); * / 설정 / 5는 굵게 펜 콤보 상자  
    pThickComboBox SelectItem(0);->

 ```  
  
2.  Save a color drawing to a file. Add the following statement to scribdoc.cpp, in the `CStroke::Serialize` method, after the `ar << (WORD)m_nPenWidth;` statement.  
  
 ```  
    ar << (COLORREF) m_penColor;  
 ```  
  
3.  Finally, load a color drawing from a file. Add the following line of code, in the `CStroke::Serialize` method, after the `m_nPenWidth = w;` statement.  
  
 ```  
    ar >> m_penColor;  
 ```  
  
4.  Now scribble in color and save your drawing to a file.  
  
 [[Sections](#top)]  
  
## Conclusion  
 You have updated the MFC Scribble application. Use this walkthrough as a guide when you modify your existing applications.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)   
 [Walkthrough: Updating the MFC Scribble Application (Part 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)

