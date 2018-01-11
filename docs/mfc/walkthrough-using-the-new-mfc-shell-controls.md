---
title: "연습: 새 MFC를 사용 하 여 컨트롤을 셸 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be882671da836f7d96f4c726753d6235735f363d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>연습: 새 MFC 셸 컨트롤 사용
이 연습에서 파일 탐색기와 비슷한 응용 프로그램을 만듭니다. 두 개의 창이 포함 된 창을 만듭니다. 왼쪽된 창에 있는 한 [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) 계층적 보기에 데스크톱을 표시 하는 개체입니다. 오른쪽 창에 있는 한 [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) 왼쪽된 창에서 선택 된 폴더의 파일을 표시 하는 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습에서는 가정를 설정한 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 사용할 **일반 개발 설정**합니다. 몇 가지 다양 한 개발 설정을 사용 중인 경우 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 이 연습에서 사용 하는 windows 기본적으로 표시 될 수 있습니다.  
  
### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 사용 하 여 새 MFC 응용 프로그램을 만들려면  
  
1.  사용 하 여는 **MFC 응용 프로그램 마법사** 새 MFC 응용 프로그램을 만듭니다. 마법사를 실행 하는 **파일** 메뉴 선택 **새로**를 선택한 후 **프로젝트**합니다. **새 프로젝트** 대화 상자가 표시 됩니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 **Visual c + +** 에서 노드는 **프로젝트 형식** 창과 선택 **MFC**합니다. 그런 다음는 **템플릿** 창 선택 **MFC 응용 프로그램**합니다. 같은 프로젝트에 대 한 이름을 입력 `MFCShellControls` 클릭 **확인**합니다. **MFC 응용 프로그램 마법사** 표시 됩니다.  
  
3.  에 **MFC 응용 프로그램 마법사** 대화 상자를 클릭 **다음**합니다. **응용 프로그램 종류** 창이 표시 됩니다.  
  
4.  에 **응용 프로그램 종류** 창 아래에서 **응용 프로그램 종류**선택을 취소는 **탭 문서** 옵션입니다. 다음으로, 선택 **단일 문서** 선택 **문서/뷰 아키텍처 지원**합니다. 아래 **스타일 프로젝트**선택, **Visual Studio**, 들어오고는 **비주얼 스타일과 색** 드롭 다운 목록 **Office 2007 (파랑 테마)**. 다른 옵션은 모두 그대로 둡니다. 클릭 **다음** 표시 하는 **복합 문서 지원** 창.  
  
5.  에 **복합 문서 지원** 창 선택 **None**합니다. 클릭 **다음** 표시 하는 **문서 템플릿 문자열** 창.  
  
6.  변경 내용이 없도록는 **문서 템플릿 문자열** 창. 클릭 **다음** 표시 하는 **데이터베이스 지원** 창.  
  
7.  에 **데이터베이스 지원** 창에서 **None** 이 응용 프로그램 데이터베이스를 사용 하지 않습니다. 클릭 **다음** 표시 하는 **사용자 인터페이스 기능** 창.  
  
8.  에 **사용자 인터페이스 기능** 창에서 다음 사항을 확인는 **메뉴 모음 및 도구 모음을 사용 하 여** 옵션을 선택 합니다. 다른 옵션은 모두 그대로 둡니다. 클릭 **다음** 표시 하는 **고급 기능** 창.  
  
9. 에 **고급 기능** 창 아래에서 **고급 기능**만 선택 **ActiveX 컨트롤** 및 **공용 컨트롤 매니페스트**합니다. 아래 **고급 프레임 창**만 선택 하는 **탐색 창** 옵션입니다. 이렇게 하면 마법사를 사용 하 여 창 왼쪽에 창을 만드는 `CMFCShellTreeCtrl` 이미 포함 합니다. 클릭 **다음** 표시 하는 **생성 된 클래스** 창.  
  
10. 아무 것도 변경 하지 않을 우리는 **생성 된 클래스** 창. 따라서 **마침** 새 MFC 프로젝트를 만들려고 합니다.  
  
11. 응용 프로그램 빌드 및 실행 하 여 만들어졌는지 확인 합니다. 응용 프로그램을 빌드하는 **빌드** 메뉴 선택 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 선택 하 여 응용 프로그램을 실행 **디버깅 시작** 에서 **디버그** 메뉴.  
  
     마법사는 자동으로 사용 하 여 창 왼쪽에 표준 메뉴 모음, 표준 도구 모음, 표준 상태 표시줄, 및 Outlook 표시줄에 있는 응용 프로그램을 만듭니다는 **폴더** 보기 및 **달력** 보기 .  
  
### <a name="to-add-the-shell-list-control-to-the-document-view"></a>문서 보기를 셸 목록 컨트롤을 추가 하려면  
  
1.  이 섹션의 인스턴스를 추가 합니다 `CMFCShellListCtrl` 마법사가 만든 보기에 있습니다. MFCShellControlsView.h에 두 번 클릭 하 여 보기 헤더 파일을 열고는 **솔루션 탐색기**합니다.  
  
     찾은 `#pragma once` 헤더 파일의 맨 위 근처에 지시문입니다. 이 코드에 대 한 헤더 파일을 포함 하도록 add 아래 즉시 `CMFCShellListCtrl`:  
  
 ```  
    #include <afxShellListCtrl.h>  
 ```  
  
     이제 형식의 멤버 변수를 추가할 `CMFCShellListCtrl`합니다. 첫째, 헤더 파일에 다음 주석을 찾습니다.  
  
 ' ' * / / 메시지 맵 함수를 생성 합니다.  
 ```  
  
     Immediately above that comment add this code:  
  
 ```  
    개인: CMFCShellListCtrl m_wndList;  
 ```  
  
2.  The **MFC Application Wizard** already created a `CMFCShellTreeCtrl` object in the `CMainFrame` class, but it is a protected member. We will access this object later. Therefore, create an accessor for it now. Open the MainFrm.h header file by double-clicking it in the **Solution Explorer**. Locate the following comment:  
  
 ``` *// Attributes  
 ```  
  
     즉시 그 아래 다음 메서드 선언을 추가 합니다.  
  
 ```  
    public: 
    CMFCShellTreeCtrl& GetShellTreeCtrl();

 ```  
  
     다음으로에서 두 번 클릭 하 여 MainFrm.cpp 소스 파일을 엽니다는 **솔루션 탐색기**합니다. 해당 파일의 맨 아래에 다음과 같은 메서드 정의 추가 합니다.  
  
 ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
 {  
    return m_wndTree;  
 }  
 ```  
  
3.  업데이트에서는 이제는 `CMFCShellControlsView` 처리 하는 클래스는 **WM_CREATE** windows 메시지입니다. MFCShellControlsView.h 헤더 파일을 열고이 코드 줄을 클릭 합니다.  
  
 ```  
    class CMFCShellControlsView : public CView  
 ```  
  
     다음에 **속성** 창 클릭는 **메시지** 아이콘입니다. 찾을 때까지 아래로 스크롤하여는 **WM_CREATE** 메시지입니다. 드롭다운 목록 옆에서 **WM_CREATE**선택,  **\<추가 > OnCreate**합니다. 메시지 처리기를 수행해 줍니다을 MFC 메시지 맵에 자동으로 업데이트 됩니다.  
  
     에 `OnCreate` 이제 만들겠습니다 메서드 우리의 `CMFCShellListCtrl` 개체입니다. 찾기의 `OnCreate` 는 MFCShellControlsView.cpp에서 메서드 정의 원본 파일 및 해당 구현을 다음 코드로 바꿉니다.  
  
 ```  
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)  
 {  
    if (CView::OnCreate(lpCreateStruct) == -1)  
    return -1;  
 
    CRect rectDummy (0,
    0,
    0,
    0);

    m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,  
    rectDummy,
    this,
    1);

 
    return 0;  
 }  
 ```  
  
4.  이전 단계를 반복 하지만 **WM_SIZE** 메시지입니다. 이렇게 하면 응용 프로그램 보기를 사용자 응용 프로그램 창 크기가 변경 될 때마다 다시 그리도록 합니다. 에 대 한 정의 `OnSize` 메서드를 다음 코드로:  
  
 ```  
    void CMFCShellControlsView::OnSize(UINT nType,
    int cx,
    int cy)  
 {  
    CView::OnSize(nType,
    cx,
    cy);

    m_wndList.SetWindowPos(NULL, -1, -1,
    cx,
    cy,  
    SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);

 }  
 ```  
  
5.  마지막 단계는 연결 하는 것은 `CMFCShellTreeCtrl` 및 `CMFCShellListCtrl` 사용 하 여 개체는 [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) 메서드. 이 메서드를 호출 하 고 나면는 `CMFCShellListCtrl` 에서 선택한 항목의 내용을 자동으로 표시 됩니다는 `CMFCShellTreeCtrl`합니다. 수행 됩니다는 `OnActivateView` 에서 재정의 되는 메서드를 [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview)합니다.  
  
     MFCShellControlsView.h 헤더 파일에 내부는 `CMFCShellControlsView` 클래스 선언, 다음 메서드 선언을 추가 합니다.  
  
 ```  
    protected: 
    virtual void OnActivateView(BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);

 ```  
  
     다음으로 MFCShellControlsView.cpp 소스 파일에이 메서드에 대 한 정의 추가 합니다.  
  
 ```  
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView)   
 {  
    if (bActivate&& AfxGetMainWnd() != NULL)  
 {  
 ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);

 }  
 
    CView::OnActivateView(bActivate,
    pActivateView,
    pDeactiveView);

 }  
 ```  
  
     메서드를 호출 하기 때문에 `CMainFrame` 추가 해야 클래스는 `#include` MFCShellControlsView.cpp 소스 파일 맨 위에 있는 지시문:  
  
 ```  
    #include "MainFrm.h"  
 ```  
  
6.  응용 프로그램 빌드 및 실행 하 여 만들어졌는지 확인 합니다. 응용 프로그램을 빌드하는 **빌드** 메뉴 선택 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 선택 하 여 실행 **디버깅 시작** 에서 **디버그** 메뉴.  
  
     선택한 항목에 대 한 세부 정보 표시 됩니다는 `CMFCShellTreeCtrl` 뷰 창에서. 노드를 클릭 하는 경우는 `CMFCShellTreeCtrl`, `CMFCShellListCtrl` 자동으로 업데이트 됩니다. 마찬가지로,에 있는 폴더를 두 번 클릭 하는 경우는 `CMFCShellListCtrl`, `CMFCShellTreeCtrl` 자동 업데이트 해야 합니다.  
  
     마우스 오른쪽 단추로 또는 목록 컨트롤의 트리 컨트롤에서 항목을 클릭 합니다. 참고가 실제 파일 탐색기를 사용 하는 경우에 따라 동일한 상황에 맞는 메뉴를 가져옵니다.  
  
## <a name="next-steps"></a>다음 단계  
  
-   마법사가 Outlook 표시줄 둘 다와 함께 만든는 **폴더** 창 및 **달력** 창. 아마도 수 없더라도 **달력** 탐색기 창에서 창. 따라서 이제 해당 창을 제거 합니다.  
  
-   `CMFCShellListCtrl` 와 같은 서로 다른 모드에서 파일을 볼 **큰 아이콘**, **작은 아이콘**, **목록**, 및 **세부 정보**합니다. 이 기능을 구현 하는 응용 프로그램을 업데이트 합니다. 참고: 참조 [Visual c + + 샘플](../visual-cpp-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습](../mfc/walkthroughs-mfc.md)

