---
title: '연습: MFC 프로젝트에 애니메이션 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f647c7621c01a18cedc8d08d1a3f344b19139a90
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121801"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>연습: MFC 프로젝트에 애니메이션 추가

이 연습에서는 Visual c + +, Microsoft Foundation 클래스 라이브러리 (MFC) 프로젝트에 기본 애니메이션된 개체를 추가 하는 방법에 설명 합니다.

이러한 작업을 수행 하는 방법을 보여 줍니다.

- MFC 응용 프로그램을 만듭니다.

- 메뉴 추가 하 고 명령을 시작 하 고 중지할 애니메이션을 추가 합니다.

- 시작 및 중지 명령에 대 한 처리기를 만듭니다.

- 프로젝트에 애니메이션된 된 개체를 추가 합니다.

- 애니메이션된 된 개체 창에서 가운데 맞춤 합니다.

- 결과 확인 합니다.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 Visual Studio가 필요합니다.

### <a name="to-create-an-mfc-application"></a>MFC 응용 프로그램을 만들려면

1. **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭합니다.

2. 에 **새 프로젝트** 아래 왼쪽된 창에서 대화 상자에서 **설치 된 템플릿**를 확장 하 고 **Visual c + +** 선택한 후 **MFC**합니다. 가운데 창에서 선택 **MFC 응용 프로그램**합니다. 에 **이름** 상자에서 입력 *MFCAnimationWalkthrough*합니다. **확인**을 클릭합니다.

3. 에 **MFC 응용 프로그램 마법사** 대화 상자를 확인 하는 **응용 프로그램 종류** 은 **여러 문서**, **프로젝트 스타일** 는 **Visual Studio**, 및 **문서/뷰 아키텍처 지원** 옵션을 선택 합니다. **마침**을 클릭합니다.

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>메뉴를 추가 하 고 다음 명령을 시작 하 고 중지할 애니메이션 추가 하려면

1. 에 **보기** 메뉴에서 **다른 창** 클릭 하 고 **리소스 뷰**합니다.

2. **리소스 뷰**로 이동는 **메뉴** 폴더를 엽니다. 두 번 클릭은 `IDR_MFCAnimationWalTYPE` 리소스를 수정 하기 위해 엽니다.

3. 메뉴 모음에서에서 **여기에 입력** 상자에서 입력 *a&nimation* 애니메이션 메뉴를 만듭니다.

4. **애니메이션**에 **여기에 입력** 상자에 입력 합니다 *시작 및 전달* Start Forward 명령을 만들 수 있습니다.

5. 아래 **Start Forward**에 **여기에 입력** 상자에 입력 합니다 *시작 및 뒤로*합니다.

6. 아래 **Start Backward**에 **여기에 입력** 상자에 입력 합니다 *s&top* 하 여 Stop 명령을 만듭니다.

7. MFCAnimationWalkthrough.rc를 저장 하 고 닫습니다.

8. **솔루션 탐색기**를 수정 하기 위해 열려는 MainFrm.cpp를 두 번 클릭 합니다. 에 `CMainFrame::OnCreate` 메서드를 여러 번 호출이 있는 섹션을 찾습니다 `lstBasicCommands.AddTail`합니다. 섹션을 바로 뒤에 다음 코드를 추가 합니다.  

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

9. 파일을 저장 하 고 닫습니다.

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>시작 부분에 대 한 처리기를 만들고 중지 명령

1. 에 **프로젝트** 메뉴를 클릭 하 여 **클래스 마법사**합니다.

2. 에 **MFC 클래스 마법사**아래 **클래스 이름**선택, `CMFCAnimationWalkthroughView`합니다.

3. 에 **명령을** 탭에 **개체 Id** 상자 선택 `ID_ANIMATION_STARTFORWARD`, 한 다음는 **메시지** 상자에서 `COMMAND`합니다. 클릭 **처리기를 추가**합니다.

4. 에 **멤버 함수 추가** 대화 상자를 클릭 **확인**합니다.

5. 에 **개체 Id** 상자 선택 `ID_ANIMATION_STARTBACKWARD`, 한 다음는 **메시지** 상자 선택 `COMMAND`합니다. 클릭 **처리기를 추가**합니다.

6. 에 **멤버 함수 추가** 대화 상자를 클릭 **확인**합니다.

7. 에 **개체 Id** 상자 선택 `ID_ANIMATION_STOP`, 한 다음는 **메시지** 상자 선택 `COMMAND`합니다. 클릭 **처리기 추가** 클릭 하 고 **확인**합니다.

8. 에 **멤버 함수 추가** 대화 상자를 클릭 **확인**합니다.

9. 에 **MFC 클래스 마법사**, 클릭 **확인**합니다.

10. 편집기에 열려 있는 MFCAnimationWalkthroughView.cpp 저장 하지만 닫지는 마세요.

### <a name="to-add-an-animated-object-to-the-project"></a>프로젝트에 애니메이션된 된 개체를 추가 하려면

1. 솔루션 탐색기에서 수정 하기 위해 열려는 MFCAnimationWalkthroughView.h를 두 번 클릭 합니다. 정의 바로 앞의 `CMFCAnimationWalkthroughView` 클래스와 애니메이션 개체 일정 충돌을 처리 하는 사용자 지정 애니메이션 컨트롤러를 만들려면 다음 코드를 추가 합니다.

    ```cpp
    class CCustomAnimationController : public CAnimationController
    {
    public:
        CCustomAnimationController()
        {
        }

        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
            CAnimationGroup* pGroupNew,
            UI_ANIMATION_PRIORITY_EFFECT priorityEffect)
        {
            return TRUE;
        }
    };
    ```

2. 끝에는 `CMFCAnimationWalkthroughView` 클래스, 다음 코드를 추가 합니다.

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

3. 후의 `DECLARE_MESSAGE_MAP()` 줄, 다음 코드를 추가 합니다.

    ```cpp
    void Animate(BOOL bDirection);
    ```

4. 파일을 저장 하 고 닫습니다.

5. MFCAnimationWalkthroughView.cpp 후 파일의 위쪽에 `#include` 문을 하지만 전에 모든 클래스 메서드를 다음 코드를 추가 합니다.

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

6. 에 대 한 생성자의 끝에 `CMFCAnimationWalkthroughView`, 다음 코드를 추가 합니다.

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

7. 찾기의 `CAnimationWalthroughView::PreCreateWindow` 메서드를 다음 코드로 바꿉니다.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

8. 찾기의 `CAnimationWalkthroughView::OnDraw` 메서드를 다음 코드로 바꿉니다.

    ```cpp
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
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
            GetRValue(m_animationColor),
            GetGValue(m_animationColor),
            GetBValue(m_animationColor));

        dc.DrawText(strRGB, rect, DT_CENTER);
        rect.top += nInfoAreaHeight;

        CBrush br;
        br.CreateSolidBrush(m_animationColor);
        CBrush* pBrushOld = dc.SelectObject(&br);

        dc.Rectangle((CRect)m_animationRect);

        dc.SelectObject(pBrushOld);
    }
    ```

9. 파일의 끝에 다음 코드를 추가 합니다.

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection  nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection  nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection  nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

10. 에 **프로젝트** 메뉴를 클릭 하 여 **클래스 마법사**합니다.

11. 에 **MFC 클래스 마법사**아래 **클래스 이름**선택, `CMFCAnimationWalkthroughView`합니다.

12. 에 **메시지** 탭에 **메시지** 상자 선택 `WM_ERASEBKGND`, 클릭 **처리기 추가**, 클릭 하 고 **확인**합니다.

13. MFCAnimationWalkthroughView.cpp, 대체 구현의 `OnEraseBkgnd` 를 다음 코드로 애니메이션된 된 개체에 깜박이 그리면 줄일 수 있습니다.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

14. 구현을 대체 `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, 및 `CMFCAnimationWalkthroughView::OnAnimationStop` 다음 코드를 사용 합니다.

    ```cpp
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

15. 파일을 저장 하 고 닫습니다.

### <a name="to-center-the-animated-object-in-the-window"></a>가운데 창에서 애니메이션된 개체

1. **솔루션 탐색기**를 수정 하기 위해 열려는 MFCAnimationWalkthroughView.h를 두 번 클릭 합니다. 끝에는 `CMFCAnimationWalkthroughView` 클래스 정의 바로 뒤 `m_animationRect`, 다음 코드를 추가 합니다.

    ```cpp
    BOOL m_bCurrentDirection;
    ```

2. 파일을 저장 하 고 닫습니다.

3. 에 **프로젝트** 메뉴를 클릭 하 여 **클래스 마법사**합니다.

4. 에 **MFC 클래스 마법사**아래 **클래스 이름**선택, `CMFCAnimationWalkthroughView`합니다.

5. 에 **메시지** 탭에 **메시지** 상자 선택 `WM_SIZE`, 클릭 **처리기 추가**, 클릭 하 고 **확인**합니다.

6. MFCAnimationWalkthroughView.cpp에 대 한 코드를 바꿉니다 `CMFCAnimationWalkthroughView::OnSize` 다음 코드를 사용 합니다.

    ```cpp
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

7. 에 대 한 생성자의 시작 부분에서 `CMFCAnimationWalkthroughView`, 다음 코드를 추가 합니다.

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

8. 맨 앞에 `CMFCAnimationWalkthroughView::Animate` 메서드를 다음 코드를 추가 합니다.

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

9. 파일을 저장 하 고 닫습니다.

### <a name="to-verify-the-results"></a>결과 확인 하려면

1. 응용 프로그램을 빌드 및 실행합니다. 에 **애니메이션** 메뉴를 클릭 하 여 **Start Forward**합니다. 사각형을 표시 하 고 가운데 영역을 입력 해야 합니다. 클릭할 때 **Start Backward**애니메이션을 역순을 클릭할 때 **중지**를 중지 해야 합니다. 사각형의 채우기 색 애니메이션 진행 됨에 따라 변경 해야 하며 현재 색 애니메이션 창의 위쪽에 표시 됩니다.

## <a name="see-also"></a>참고자료

[연습](../mfc/walkthroughs-mfc.md)  
