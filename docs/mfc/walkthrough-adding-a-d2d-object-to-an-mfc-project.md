---
title: '연습: MFC 프로젝트에 D2D 개체 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7985b36c0eeaa7adf5441a7a6fbb3314bac8353f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384022"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>연습: MFC 프로젝트에 D2D 개체 추가
이 연습에서는 기본 Direct2D를 추가 하는 방법에 설명 (D2D) Visual c + +, Microsoft Foundation 클래스 라이브러리 (MFC) 프로젝트 개체를 출력 하는 응용 프로그램에 다음 프로젝트를 빌드합니다 "Hello, world" 그라데이션 배경의 합니다.  
  
 이러한 작업을 수행 하는 방법을 보여 줍니다.  
  
-   MFC 응용 프로그램을 만듭니다.  
  
-   단색 브러시 및 선형 그라데이션 브러시를 만듭니다.  
  
-   그라데이션 브러시를 수정 하 여 창 크기를 조정할 때 적절 하 게 변경 합니다.  
  
-   D2D 그리기 처리기를 구현 합니다.  
  
-   결과 확인 합니다.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 Visual Studio가 필요합니다.  
  
### <a name="to-create-an-mfc-application"></a>MFC 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  에 **새 프로젝트** 아래 왼쪽된 창에서 대화 상자에서 **설치 된 템플릿**를 확장 하 고 **Visual c + +** 선택한 후 **MFC**합니다. 가운데 창에서 선택 **MFC 응용 프로그램**합니다. **이름** 상자에 `MFCD2DWalkthrough`을 입력합니다. **확인**을 클릭합니다.  
  
3.  에 **MFC 응용 프로그램 마법사**, 클릭 **마침** 모든 설정을 변경 하지 않고 있습니다.  
  
### <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>단색 브러시 및 선형 그라데이션 브러시를 만들려면  
  
1.  **솔루션 탐색기**에 **MFCD2DWalkthrough** 프로젝트에 **헤더 파일** 폴더를 열고 MFCD2DWalkthroughView.h 합니다. 다음 코드를 추가 하는 `CMFCD2DWalkthroughView` 세 개의 데이터 변수를 만드는 클래스입니다.  
  
 ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
 ```  
  
     파일을 저장 하 고 닫습니다.  
  
2.  에 **소스 파일** 폴더를 열고 MFCD2DWalkthroughView.cpp 합니다. 에 대 한 생성자에는 `CMFCD2DWalkthroughView` 클래스, 다음 코드를 추가 합니다.  
  
 ' ' * / /이 창에 대 한 D2D 지원을 사용 하도록 설정 합니다.  
    EnableD2DSupport();

 * / / D2D 리소스를 초기화 합니다.  
    m_pBlackBrush 새 CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black)); =

 
    m_pTextFormat = 새 CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);

    m_pTextFormat get ()-> SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);->

 m_pTextFormat get ()-> SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);->

 
    D2D1_GRADIENT_STOP gradientStops [2].  
 
    [0] gradientStops.color D2D1::ColorF(D2D1::ColorF::White); =

    [0] gradientStops.position 0.f; =  
    [1] gradientStops.color D2D1::ColorF(D2D1::ColorF::Indigo); =

    [1] gradientStops.position 1.f; =  
 
    m_pLinearGradientBrush 새 CD2DLinearGradientBrush(GetRenderTarget() =   
    gradientStops, ARRAYSIZE(gradientStops),  
    D2D1::LinearGradientBrushProperties (D2D1::Point2F (0, 0), D2D1::Point2F (0, 0)));

 ```  
  
     Save the file and close it.  
  
### To modify the gradient brush so that it will change appropriately when the window is resized  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, in the **Messages** box, select `WM_SIZE` and then click **Add Handler**. This action adds the `OnSize` message handler to the `CMFCD2DWalkthroughView` class.  
  
4.  In the **Existing handlers** box, select `OnSize`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnSize` method. At the end of the method, add the following code.  
  
 ```  
    m_pLinearGradientBrush SetEndPoint (CPoint (cx, cy));->

 ```  
  
     Save the file and close it.  
  
### To implement a D2D drawing handler  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, click **Add Custom Message**.  
  
4.  In the **Add Custom Message** dialog box, in the **Custom Windows Message** box, type `AFX_WM_DRAW2D`. In the **Message handler name** box, type `OnDraw2D`. Select the **Registered Message** option and then click **OK**. This action adds a message handler for the `AFX_WM_DRAW2D` message to the `CMFCD2DWalkthroughView` class.  
  
5.  In the **Existing handlers** box, select `OnDraw2D`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnDraw2D` method. Use the following code for the `CMFCD2DWalkthroughView::OnDrawD2D` method.  
  
 ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
 CHwndRenderTarget pRenderTarget (CHwndRenderTarget *) lParam; =  
    ASSERT_VALID(pRenderTarget);

 
    CRect rect;  
    GetClientRect(rect);

 
    pRenderTarget FillRectangle (rect, m_pLinearGradientBrush);->

    pRenderTarget DrawText (_T ("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);->

 
    TRUE를 반환 합니다.  
 }  
 ```  
  
     Save the file and close it.  
  
### To verify the results  
  
1.  Build and run the application. It should have a gradient rectangle that changes when you resize the window. “Hello World!” should be displayed in the center of the rectangle.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)

