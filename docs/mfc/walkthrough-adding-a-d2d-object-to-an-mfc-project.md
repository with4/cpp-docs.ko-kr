---
title: "연습: MFC 프로젝트에 D2D 개체 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D2D[MFC]"
  - "MFC, D2D"
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 20
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: MFC 프로젝트에 D2D 개체 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 Visual C\+\+ MFC 라이브러리 프로젝트에 기본 D2D\(Direct 2D\) 개체를 추가한 다음 이 프로젝트를 그라데이션 배경에 "Hello, world"를 출력하는 응용 프로그램으로 빌드하는 방법을 배웁니다.  
  
 연습에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
-   MFC 응용 프로그램 만들기  
  
-   단색 브러시 및 선형 그라데이션 브러시 만들기  
  
-   창 크기를 조정할 때 적절하게 변경되도록 그라데이션 브러시 수정  
  
-   D2D 그리기 처리기 구현  
  
-   결과 확인  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## 사전 요구 사항  
 To complete this walkthrough, you must have Visual Studio.  
  
### MFC 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자 왼쪽 창의 **설치된 템플릿**에서 **Visual C\+\+**를 확장하고 **MFC**를 선택합니다.  가운데 창에서 **MFC 응용 프로그램**을 선택합니다.  **이름** 상자에 `MFCD2DWalkthrough`를 입력합니다.  **확인**을 클릭합니다.  
  
3.  **MFC 응용 프로그램 마법사**에서 설정을 변경하지 않고 **마침**을 클릭합니다.  
  
### 단색 브러시 및 선형 그라데이션 브러시를 만들려면  
  
1.  **솔루션 탐색기**에서 **MFCD2DWalkthrough** 프로젝트의 **헤더 파일** 폴더에 있는 MFCD2DWalkthroughView.h를 엽니다.  `CMFCD2DWalkthroughView` 클래스에 다음 코드를 추가하여 세 개의 데이터 변수를 만듭니다.  
  
    ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
    ```  
  
     파일을 저장한 다음 닫습니다.  
  
2.  **소스 파일** 폴더에서 MFCD2DWalkthroughView.cpp를 엽니다.  `CMFCD2DWalkthroughView` 클래스의 생성자에 다음 코드를 추가합니다.  
  
    ```  
    // Enable D2D support for this window:  
    EnableD2DSupport();  
  
    // Initialize D2D resources:  
    m_pBlackBrush = new CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));  
  
    m_pTextFormat = new CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);  
    m_pTextFormat->Get()->SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);  
    m_pTextFormat->Get()->SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);  
  
    D2D1_GRADIENT_STOP gradientStops[2];  
  
    gradientStops[0].color = D2D1::ColorF(D2D1::ColorF::White);  
    gradientStops[0].position = 0.f;  
    gradientStops[1].color = D2D1::ColorF(D2D1::ColorF::Indigo);  
    gradientStops[1].position = 1.f;  
  
    m_pLinearGradientBrush = new CD2DLinearGradientBrush(GetRenderTarget(),   
        gradientStops, ARRAYSIZE(gradientStops),  
        D2D1::LinearGradientBrushProperties(D2D1::Point2F(0, 0), D2D1::Point2F(0, 0)));  
    ```  
  
     파일을 저장한 다음 닫습니다.  
  
### 창 크기를 조정할 때 적절하게 변경되도록 그라데이션 브러시를 수정하려면  
  
1.  **프로젝트** 메뉴에서 **클래스 마법사**를 클릭합니다.  
  
2.  **MFC 클래스 마법사**의 **클래스 이름**에서 `CMFCD2DWalkthroughView`를 선택합니다.  
  
3.  **메시지** 탭의 **메시지** 상자에서 `WM_SIZE`를 선택하고 **처리기 추가**를 클릭합니다.  이렇게 하면 `CMFCD2DWalkthroughView` 클래스에 `OnSize` 메시지 처리기가 추가됩니다.  
  
4.  **기존 처리기** 상자에서 `OnSize`를 선택합니다.  **코드 편집**을 클릭하여 `CMFCD2DWalkthroughView::OnSize` 메서드를 표시합니다.  메서드의 끝에 다음 코드를 추가합니다.  
  
    ```  
    m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));  
    ```  
  
     파일을 저장한 다음 닫습니다.  
  
### D2D 그리기 처리기를 구현하려면  
  
1.  **프로젝트** 메뉴에서 **클래스 마법사**를 클릭합니다.  
  
2.  **MFC 클래스 마법사**의 **클래스 이름**에서 `CMFCD2DWalkthroughView`를 선택합니다.  
  
3.  **메시지** 탭에서 **사용자 지정 메시지 추가**를 클릭합니다.  
  
4.  **사용자 지정 메시지 추가** 대화 상자의 **사용자 지정 Windows 메시지** 상자에 `AFX_WM_DRAW2D`를 입력합니다.  **메시지 처리기 이름** 상자에 `OnDraw2D`를 입력합니다.  **등록된 메시지** 옵션을 선택하고 **확인**을 클릭합니다.  이렇게 하면 `CMFCD2DWalkthroughView` 클래스에 `AFX_WM_DRAW2D` 메시지에 대한 메시지 처리기가 추가됩니다.  
  
5.  **기존 처리기** 상자에서 `OnDraw2D`를 선택합니다.  **코드 편집**을 클릭하여 `CMFCD2DWalkthroughView::OnDraw2D` 메서드를 표시합니다.  `CMFCD2DWalkthroughView::OnDrawD2D` 메서드에 대한 다음 코드를 사용합니다.  
  
    ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
        CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;  
        ASSERT_VALID(pRenderTarget);  
  
        CRect rect;  
        GetClientRect(rect);  
  
        pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);  
        pRenderTarget->DrawText(_T("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);  
  
        return TRUE;  
    }  
    ```  
  
     파일을 저장한 다음 닫습니다.  
  
### 결과를 확인하려면  
  
1.  응용 프로그램을 빌드하고 실행합니다.  창의 크기를 변경하면 그라데이션 사각형이 변경되고 "Hello World\!"가 사각형의 가운데에 표시되어야 합니다.  
  
## 참고 항목  
 [연습](../mfc/walkthroughs-mfc.md)