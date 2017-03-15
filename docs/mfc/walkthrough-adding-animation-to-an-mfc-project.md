---
title: "연습: MFC 프로젝트에 애니메이션 추가 | Microsoft Docs"
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
  - "애니메이션[MFC]"
  - "MFC, 애니메이션"
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 연습: MFC 프로젝트에 애니메이션 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 Visual C\+\+ MFC 라이브러리 프로젝트에 애니메이션이 적용된 기본 개체를 추가하는 방법을 배웁니다.  
  
 연습에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
-   MFC 응용 프로그램 만들기  
  
-   메뉴를 추가한 다음 애니메이션 시작 및 중지 명령 추가  
  
-   시작 및 중지 명령에 대한 처리기 만들기  
  
-   프로젝트에 애니메이션이 적용된 개체 추가  
  
-   애니메이션이 적용된 개체를 창의 가운데에 맞추기  
  
-   결과 확인  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 Visual Studio가 필요합니다.  
  
### MFC 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자 왼쪽 창의 **설치된 템플릿**에서 **Visual C\+\+**를 확장하고 **MFC**를 선택합니다.  가운데 창에서 **MFC 응용 프로그램**을 선택합니다.  **이름** 상자에 `MFCAnimationWalkthrough`를 입력합니다.  **확인**을 클릭합니다.  
  
3.  **MFC 응용 프로그램 마법사** 대화 상자에서 **응용 프로그램 종류**가 **여러 문서**이고, **프로젝트 스타일**이 **Visual Studio**이며, **문서\/뷰 아키텍처 지원** 옵션이 선택되어 있는지 확인합니다.  **마침**을 클릭합니다.  
  
### 메뉴를 추가한 다음 애니메이션 시작 및 중지 명령을 추가하려면  
  
1.  **보기** 메뉴에서 **다른 창**을 가리킨 다음 **리소스 뷰**를 클릭합니다.  
  
2.  **리소스 뷰**에서 **메뉴** 폴더를 찾아 엽니다.  `IDR_MFCAnimationWalTYPE` 리소스를 수정하기 위해 두 번 클릭하여 엽니다.  
  
3.  메뉴 모음의 **여기에 입력** 상자에 `A&nimation`을 입력하여 Animation 메뉴를 만듭니다.  
  
4.  **Animation**의 **여기에 입력** 상자에 `Start &Forward`를 입력하여 Start Forward 명령을 만듭니다.  
  
5.  **Start Forward**의 **여기에 입력** 상자에 `Start &Backward`를 입력합니다.  
  
6.  **Start Backward**의 **여기에 입력** 상자에 `S&top`을 입력하여 Stop 명령을 만듭니다.  
  
7.  MFCAnimationWalkthrough.rc를 저장하고 닫습니다.  
  
8.  **솔루션 탐색기**에서 MainFrm.cpp를 수정하기 위해 두 번 클릭하여 엽니다.  `CMainFrame::OnCreate` 메서드에서 `lstBasicCommands.AddTail`에 대한 호출이 여러 개 있는 섹션을 찾습니다.  이 섹션 바로 뒤에 다음 코드를 추가합니다.  
  
    ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);  
    ```  
  
9. 파일을 저장한 다음 닫습니다.  
  
### 시작 및 중지 명령에 대한 처리기를 만들려면  
  
1.  **프로젝트** 메뉴에서 **클래스 마법사**를 클릭합니다.  
  
2.  **MFC 클래스 마법사**의 **클래스 이름**에서 `CMFCAnimationWalkthroughView`를 선택합니다.  
  
3.  **명령** 탭의 **개체 ID** 상자에서 `ID_ANIMATION_STARTFORWARD`를 선택하고 **메시지** 상자에서 `COMMAND`를 선택합니다.  **처리기 추가**를 클릭합니다.  
  
4.  **멤버 함수 추가** 대화 상자에서 **확인**을 클릭합니다.  
  
5.  **개체 ID** 상자에서 `ID_ANIMATION_STARTBACKWARD`를 선택하고 **메시지** 상자에서 `COMMAND`를 선택합니다.  **처리기 추가**를 클릭합니다.  
  
6.  **멤버 함수 추가** 대화 상자에서 **확인**을 클릭합니다.  
  
7.  **개체 ID** 상자에서 `ID_ANIMATION_STOP`을 선택하고 **메시지** 상자에서 `COMMAND`를 선택합니다.  **처리기 추가**를 클릭하고 **확인**을 클릭합니다.  
  
8.  **멤버 함수 추가** 대화 상자에서 **확인**을 클릭합니다.  
  
9. **MFC 클래스 마법사**에서 **확인**을 클릭합니다.  
  
10. 편집기에 열려 있는 MFCAnimationWalkthroughView.cpp를 저장하고 닫지는 않습니다.  
  
### 프로젝트에 애니메이션이 적용된 개체를 추가하려면  
  
1.  솔루션 탐색기에서 MFCAnimationWalkthroughView.h를 수정하기 위해 두 번 클릭하여 엽니다.  `CMFCAnimationWalkthroughView` 클래스 정의 바로 앞에 다음 코드를 추가하여 애니메이션 개체와의 일정 충돌을 처리할 사용자 지정 애니메이션 컨트롤러를 만듭니다.  
  
    ```  
    class CCustomAnimationController : public CAnimationController  
    {  
    public:  
        CCustomAnimationController()  
        {  
        }  
  
        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled, CAnimationGroup* pGroupNew, UI_ANIMATION_PRIORITY_EFFECT priorityEffect)  
        {  
            return TRUE;  
        }  
    };  
    ```  
  
2.  `CMFCAnimationWalkthroughView` 클래스의 끝에 다음 코드를 추가합니다.  
  
    ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
    ```  
  
3.  `DECLARE_MESSAGE_MAP()` 줄 뒤에 다음 코드를 추가합니다.  
  
    ```  
    void Animate(BOOL bDirection);  
    ```  
  
4.  파일을 저장한 다음 닫습니다.  
  
5.  MFCAnimationWalkthroughView.cpp 파일 맨 위에서 `#include` 문 뒤 및 클래스 메서드 앞에 다음 코드를 추가합니다.  
  
    ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
    ```  
  
6.  `CMFCAnimationWalkthroughView`의 생성자 끝에 다음 코드를 추가합니다.  
  
    ```  
    m_animationController.EnableAnimationTimerEventHandler();  
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);  
  
    m_animationColor = RGB(255, 255, 255);  
    m_animationRect = CRect(0, 0, 0, 0);  
  
    m_animationColor.SetID(-1, nAnimationGroup);  
    m_animationRect.SetID(-1, nAnimationGroup);  
  
    m_animationController.AddAnimationObject(&m_animationColor);  
    m_animationController.AddAnimationObject(&m_animationRect);  
    ```  
  
7.  `CAnimationWalthroughView::PreCreateWindow` 메서드를 찾아 다음 코드로 바꿉니다.  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
    {  
        // TODO: Modify the Window class or styles here by modifying  
        //  the CREATESTRUCT cs  
  
        m_animationController.SetRelatedWnd(this);  
        return CView::PreCreateWindow(cs);  
    }  
    ```  
  
8.  `CAnimationWalkthroughView::OnDraw` 메서드를 찾아 다음 코드로 바꿉니다.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
    {  
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();  
        ASSERT_VALID(pDoc);  
        if (!pDoc)  
            return;  
  
        // TODO: add draw code for native data here  
        CMemDC dcMem(*pDC, this);  
        CDC& dc = dcMem.GetDC();  
  
        CRect rect;  
        GetClientRect(rect);  
  
        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));  
  
        CString strRGB;  
        strRGB.Format(_T("Fill Color is: %d; %d; %d"), GetRValue(m_animationColor), GetGValue(m_animationColor), GetBValue(m_animationColor));  
  
        dc.DrawText(strRGB, rect, DT_CENTER);  
        rect.top += nInfoAreaHeight;  
  
        CBrush br;  
  
        br.CreateSolidBrush(m_animationColor);  
        CBrush* pBrushOld = dc.SelectObject(&br);  
  
        dc.Rectangle((CRect)m_animationRect);  
        dc.SelectObject(pBrushOld);  
    }  
    ```  
  
9. 파일의 끝에 다음 코드를 추가합니다.  
  
    ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
    {  
        static UI_ANIMATION_SECONDS duration = 3;  
        static DOUBLE dblSpeed = 35.;  
        static BYTE nStartColor = 50;  
        static BYTE nEndColor = 255;  
  
        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;  
  
        CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);  
        CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);  
        CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);  
  
        m_animationColor.AddTransition(pRedTransition, pGreenTransition, pBlueTransition);  
  
        CRect rectClient;  
        GetClientRect(rectClient);  
        rectClient.top += nInfoAreaHeight;  
  
        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;  
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;  
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;  
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;  
  
        CLinearTransition* pLeftTransition = new CLinearTransition(duration, nLeftFinal);  
        CLinearTransition* pTopTransition = new CLinearTransition(duration, nTopFinal);  
        CLinearTransition* pRightTransition = new CLinearTransition(duration, nRightFinal);  
        CLinearTransition* pBottomTransition = new CLinearTransition(duration, nBottomFinal);  
  
        m_animationRect.AddTransition(pLeftTransition, pTopTransition, pRightTransition, pBottomTransition);  
  
        CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();  
        CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup, pBlueTransition);  
  
        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
  
        m_animationController.AnimateGroup(nAnimationGroup);  
    }  
    ```  
  
10. **프로젝트** 메뉴에서 **클래스 마법사**를 클릭합니다.  
  
11. **MFC 클래스 마법사**의 **클래스 이름**에서 `CMFCAnimationWalkthroughView`를 선택합니다.  
  
12. **메시지** 탭의 **메시지** 상자에서 `WM_ERASEBKGND`를 선택하고 **처리기 추가**를 클릭한 다음 **확인**을 클릭합니다.  
  
13. MFCAnimationWalkthroughView.cpp에서 `OnEraseBkgnd`의 구현을 다음 코드로 바꾸어 애니메이션이 적용된 개체가 다시 그려질 때의 깜빡임을 줄입니다.  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
    {  
        return TRUE;  
    }  
    ```  
  
14. `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward` 및 `CMFCAnimationWalkthroughView::OnAnimationStop`의 구현을 다음 코드로 바꿉니다.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()  
    {  
        Animate(TRUE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()  
    {  
        Animate(FALSE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStop()  
    {  
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();  
        if (pManager != NULL)  
        {  
            pManager->AbandonAllStoryboards();  
        }  
    }  
  
    ```  
  
15. 파일을 저장한 다음 닫습니다.  
  
### 애니메이션이 적용된 개체를 창의 가운데에 맞추려면  
  
1.  **솔루션 탐색기**에서 MFCAnimationWalkthroughView.h를 수정하기 위해 두 번 클릭하여 엽니다.  `CMFCAnimationWalkthroughView` 클래스의 끝에서 `m_animationRect` 정의 바로 뒤에 다음 코드를 추가합니다.  
  
    ```  
    BOOL m_bCurrentDirection;  
    ```  
  
2.  파일을 저장한 다음 닫습니다.  
  
3.  **프로젝트** 메뉴에서 **클래스 마법사**를 클릭합니다.  
  
4.  **MFC 클래스 마법사**의 **클래스 이름**에서 `CMFCAnimationWalkthroughView`를 선택합니다.  
  
5.  **메시지** 탭의 **메시지** 상자에서 `WM_SIZE`를 선택하고 **처리기 추가**를 클릭한 다음 **확인**을 클릭합니다.  
  
6.  MFCAnimationWalkthroughView.cpp에서 `CMFCAnimationWalkthroughView::OnSize`의 코드를 다음 코드로 바꿉니다.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
  
        CRect rect;  
        GetClientRect(rect);  
        rect.top += nInfoAreaHeight;  
  
        CRect rectAnim = m_animationRect;  
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,   
                                rect.CenterPoint().y - rectAnim.Height() / 2),   
                                rectAnim.Size());  
  
        if (m_animationController.IsAnimationInProgress())  
        {  
            Animate(m_bCurrentDirection);  
        }  
    }  
    ```  
  
7.  `CMFCAnimationWalkthroughView`의 생성자 시작 부분에 다음 코드를 추가합니다.  
  
    ```  
    m_bCurrentDirection = TRUE;  
    ```  
  
8.  `CMFCAnimationWalkthroughView::Animate` 메서드의 시작 부분에 다음 코드를 추가합니다.  
  
    ```  
    m_bCurrentDirection = bDirection;  
    ```  
  
9. 파일을 저장한 다음 닫습니다.  
  
### 결과를 확인하려면  
  
1.  응용 프로그램을 빌드하고 실행합니다.  **Animation** 메뉴에서 **Start Forward**를 클릭합니다.  사각형이 나타나고 가운데 영역이 채워집니다.  **Start Backward**를 클릭하면 애니메이션이 역방향으로 재생되고, **Stop**을 클릭하면 애니메이션이 중지됩니다.  애니메이션이 진행되면서 사각형의 채우기 색이 변경되고 현재 색은 애니메이션 창의 위쪽에 표시됩니다.  
  
## 참고 항목  
 [연습](../mfc/walkthroughs-mfc.md)