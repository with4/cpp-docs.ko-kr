---
title: "연습: 새 MFC 셸 컨트롤 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "셸 컨트롤(MFC)"
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 새 MFC 셸 컨트롤 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 파일 탐색기와 비슷한 응용 프로그램을 만듭니다.  두 개의 창이 포함된 창을 만듭니다.  왼쪽 창에는 바탕 화면을 계층적 뷰에 표시하는 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) 개체가 포함됩니다.  오른쪽 창에는 왼쪽 창에서 선택한 폴더의 파일을 표시하는 [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) 개체가 포함됩니다.  
  
## 사전 요구 사항  
 이 연습에서는 **일반 개발 설정**을 사용하기 위하여 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]을 설정했다고 가정합니다.  다른 개발 설정을 사용하는 경우, 이 연습에서 사용하는 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 창이 기본적으로 표시되지 않을 수도 있습니다.  
  
### MFC 응용 프로그램 마법사를 사용하여 새 MFC 응용 프로그램을 만들려면  
  
1.  새 MFC 응용 프로그램을 만들기 위하여 **MFC 응용 프로그램 마법사**를 사용합니다.  마법사를 실행하려면, **파일** 메뉴에서 **새로 만들기**를 선택한 후, **프로젝트**를 선택합니다.  **새 프로젝트** 대화 상자가 표시됩니다.  
  
2.  **새 프로젝트** 대화 상자에서, **Visual C\+\+** 노드를 확장하고, **프로젝트 종류** 창에서 **MFC**를 선택합니다.  그리고 나서, **템플릿** 창에서 **MFC 응용 프로그램**을 선택합니다.  프로젝트의 이름을 입력하고 \(예 : `MFCShellControls`\) **확인**을 클릭합니다.  **MFC 응용 프로그램 마법사**가 표시됩니다.  
  
3.  **MFC 응용 프로그램 마법사** 대화 상자에서 **다음**을 클릭합니다.  **응용 프로그램 유형** 창이 나타납니다.  
  
4.  **응용 프로그램 유형**창에서, **응용 프로그램 종류** 아래의 **탭 문서** 옵션을 설정 해제합니다.  그런 다음 **단일 문서**를 선택하고, **문서\/뷰 아키텍처 지원**을 선택합니다.  **프로젝트 스타일** 아래의 **Visual Studio**를 선택하고, **비주얼 스타일 및 색** 드롭 다운 목록에서 선택 **Office 2007 \(파랑 테마\)**을 선택합니다.  다른 옵션은 모두 그대로 둡니다.  **복합 문서 지원** 창을 표시하기 위해 **다음**을 클릭합니다.  
  
5.  **복합 문서 지원** 창에서 **없음**을 선택합니다.  **문서 템플릿 문자열** 창을 표시하기 위해 **다음**을 클릭합니다.  
  
6.  **문서 템플릿 문자열** 창에서 어떠한 변경도 만들지 마십시오.  **데이터베이스 지원** 창을 표시하기 위해 **다음**을 클릭합니다.  
  
7.  이 응용 프로그램 데이터베이스를 사용 하지 않으므로 **데이터베이스 지원** 창에서 **없음**을 선택합니다.  **사용자 인터페이스 기능** 창을 표시하기 위해 **다음**을 클릭합니다.  
  
8.  **사용자 인터페이스 기능** 창에서, **메뉴 모음과 도구 모음을 사용** 옵션이 선택되었는지 확인합니다.  다른 옵션은 모두 그대로 둡니다.  **고급 기능** 창을 표시하기 위해 **다음**을 클릭합니다.  
  
9. **고급 기능** 창의 **고급 기능** 아래에서, **ActiveX 컨트롤**과 **공용 컨트롤 매니페스트**만을 선택합니다.  **고급 프레임 창** 아래에서, **탐색 창** 옵션만을 선택합니다.  이는 마법사가 창의 왼쪽에 이미 포함된 `CMFCShellTreeCtrl`를 생성하게 합니다.  **생성된 클래스** 창을 표시하기 위해 **다음**을 클릭합니다.  
  
10. 우리는 **생성된 클래스** 창에서 어떠한 변경도 하지 않을 것입니다.  따라서, **완료**를 클릭하여 새 MFC 프로젝트를 만듭니다.  
  
11. 응용 프로그램을 빌드하고 실행하여 제대로 만들어졌는지 확인합니다.  응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작**을 선택하여 응용 프로그램을 실행합니다.  
  
     마법사는 왼쪽 창에 **폴더** 보기 및 **일정** 보기와 함께 표준 메뉴 모음, 표준 도구 모음, 표준 상태 표시줄 및 Outlook 표시줄을 자동으로 생성합니다.  
  
### 문서 보기에 셸 목록 컨트롤을 추가 하려면  
  
1.  이 영역에서는  마법사가 만든 보기에 `CMFCShellListCtrl` 인스턴스를 추가합니다.  헤더 파일 보기에서 MFCShellControlsView.h를 두 번 클릭하여 **솔루션 탐색기**를 여십시오.  
  
     `#pragma once` 지시문을 헤더 파일의 맨 위쪽 근처에서 찾습니다.  그 바로 밑에 이 코드를 추가하여  `CMFCShellListCtrl` 를 위한 헤더 파일을 포함하십시오.  
  
    ```  
    #include <afxShellListCtrl.h>  
    ```  
  
     `CMFCShellListCtrl` 형식의 멤버 변수를 추가하십시오.  먼저, 헤더 파일에서 다음과 같은 주석을 찾습니다.  
  
    ```  
    // Generated message map functions  
    ```  
  
     그 주석 바로 위에 이 코드를 삽입합니다.  
  
    ```  
    private:  
        CMFCShellListCtrl m_wndList;  
    ```  
  
2.  **MFC 응용 프로그램 마법사**는 이미 `CMainFrame` 클래스에서 `CMFCShellTreeCtrl` 개체를 만들었지만, 이것은 보호된 멤버입니다.  이 개체에는 나중에 액세스할 것입니다.  따라서, 이제 그를 위한 접근자를 만듭니다.  MainFrm.h 헤더 파일을 **솔루션 탐색기**에서 두 번 클릭하여 엽니다.  다음 주석을 찾습니다.  
  
    ```  
    // Attributes  
    ```  
  
     그 바로 아래에, 다음 메서드 선언을 추가합니다.  
  
    ```  
    public:  
        CMFCShellTreeCtrl& GetShellTreeCtrl();  
    ```  
  
     다음에, MainFrm.cpp 소스 파일을 **솔루션 탐색기**에서 두 번 클릭하여 엽니다.  해당 파일의 맨 아래에 다음 메서드 정의를 추가합니다.  
  
    ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
    {  
        return m_wndTree;  
    }  
    ```  
  
3.  이제 **WM\_CREATE** 창 메시지를 처리하기 위하여 `CMFCShellControlsView` 클래스를 업데이트합니다.  MFCShellControlsView.h 헤더 파일을 열고 코드의 이 줄을 클릭합니다.  
  
    ```  
    class CMFCShellControlsView : public CView  
    ```  
  
     그 다음, **속성** 창에서, **메시지** 버튼을 클릭합니다.  **WM\_CREATE** 메시지를 찾을 때까지 아래로 스크롤합니다.  드롭다운 목록 옆의 **WM\_CREATE**에서 **생성시 \<추가\>**를 선택합니다.  이는 메시지 처리기를 생성하고 자동으로 MFC 메시지 맵을 업데이트합니다.  
  
     이제 `OnCreate` 메서드에서 `CMFCShellListCtrl` 개체를 생성합니다.   MFCShellControlsView.cpp 소스 파일에서 `OnCreate` 메서드 정의를 찾고, 그 구현을 다음 코드로 대체합니다.  
  
    ```  
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)  
    {  
        if (CView::OnCreate(lpCreateStruct) == -1)  
            return -1;  
  
        CRect rectDummy (0, 0, 0, 0);  
        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,  
            rectDummy, this, 1);  
  
        return 0;  
    }  
    ```  
  
4.  **\-WM\_SIZE** 메시지가 없다면 이전 단계를 반복합니다.  이는 응용 프로그램 보기로 하여금 사용자가 응용 프로그램 창의 크기를 변경할 때마다 다시 그려지도록 합니다.  `OnSize` 메서드 정의를 다음 코드로 바꿉니다.  
  
    ```  
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,  
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);  
    }  
    ```  
  
5.  `CMFCShellTreeCtrl` 및 `CMFCShellListCtrl` 개체에 연결하기 위한 마지막 단계는 [CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md) 메서드를 사용하는 것입니다.  이 메서드를 호출한 후, `CMFCShellListCtrl`는 자동적으로  `CMFCShellTreeCtrl` 에서 선택된 항목의 내용을 표시합니다.  우리는 [CView::OnActivateView](../Topic/CView::OnActivateView.md)에서 재정의된 `OnActivateView` 메서드에서 이를 실행할 것입니다.  
  
     MFCShellControlsView.h 헤더 파일에서, `CMFCShellControlsView` 클래스 선언의 안에 다음 메서드 선언을 추가하십시오.  
  
    ```  
    protected:  
        virtual void OnActivateView(BOOL bActivate,  
            CView* pActivateView,  
            CView* pDeactiveView);  
    ```  
  
     다음으로, MFCShellControlsView.cpp 소스 파일에 이 메서드 정의를 추가합니다.  
  
    ```  
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,  
        CView* pActivateView,  
        CView* pDeactiveView)   
    {  
        if (bActivate && AfxGetMainWnd() != NULL)  
        {  
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);  
        }  
  
        CView::OnActivateView(bActivate, pActivateView, pDeactiveView);  
    }  
    ```  
  
     `CMainFrame` 클래스의 메서드를 호출하기 때문에, `#include`를 MFCShellControlsView.cpp 소스 파일 맨 위에 지시문을 추가해야 합니다.  
  
    ```  
    #include "MainFrm.h"  
    ```  
  
6.  응용 프로그램을 빌드하고 실행하여 제대로 만들어졌는지 확인합니다.  응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  응용 프로그램이 성공적으로 빌드되면 **디버그** 메뉴에서 **디버깅 시작**을 선택하여 응용 프로그램을 실행합니다.  
  
     이제 `CMFCShellTreeCtrl` 보기 창에서 선택된 항목에 대한 자세한 정보를 볼 수 있습니다.  `CMFCShellTreeCtrl`, `CMFCShellListCtrl`의 노드를 클릭하면 자동으로 업데이트됩니다.  마찬가지로, `CMFCShellListCtrl`, `CMFCShellTreeCtrl`의 폴더를 두 번 클릭 하면 자동으로 업데이트됩니다.  
  
     트리 컨트롤 혹은 목록 컨트롤의 항목을 마우스 오른쪽 단추로 클릭합니다.  실제 파일 탐색기를 사용하는 경우와 같은 상황 메뉴를 가져온다는 점에 유의하십시오.  
  
## 다음 단계  
  
-   마법사는 **폴더** 창 과 **일정** 창을 포함한 Outlook 표시줄을 생성합니다.  탐색기 창 안에 **일정** 창이 위치하는 것은 어울리지 않습니다.  따라서, 이 창을 제거합니다.  
  
-   `CMFCShellListCtrl`은 **큰 아이콘**, **작은 아이콘**, **목록** 및 **자세히** 등의 다양한 모드로 파일 보기를 지원합니다.  이 기능을 구현하기 위해 응용 프로그램을 업데이트합니다.  힌트: [Visual C\+\+ 샘플](../top/visual-cpp-samples.md)를 참조하십시오.  
  
## 참고 항목  
 [연습](../mfc/walkthroughs-mfc.md)