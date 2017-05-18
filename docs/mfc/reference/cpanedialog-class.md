---
title: "CPaneDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog::OnLButtonDblClk method
- CPaneDialog::OnLButtonDown method
- CPaneDialog::CreateObject method
- CPaneDialog::OnUpdateCmdUI method
- CPaneDialog constructor
- CPaneDialog::OnEraseBkgnd method
- CPaneDialog class
- CPaneDialog::OnWindowPosChanging method
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 85c7e338382758dd809fb770c5ab14860e362da8
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cpanedialog-class"></a>CPaneDialog 클래스
`CPaneDialog` 클래스는 도킹 가능한 모덜리스 대화 상자를 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|기본 생성자입니다.|  
|`CPaneDialog::~CPaneDialog`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|도킹 가능한 대화 상자를 만들고 연결 하는 `CPaneDialog` 개체입니다.|  
|`CPaneDialog::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CPaneDialog::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|처리는 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) 메시지입니다. (다시 정의 하는 `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|처리는 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) 메시지입니다. (다시 정의 하는 [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|처리는 [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) 메시지입니다. (다시 정의 하는 [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|처리는 [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) 메시지입니다. (다시 정의 하는 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|대화 상자 창을 업데이트 하려면 프레임 워크에 의해 호출 됩니다. (재정의 [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|처리는 [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) 메시지입니다. (다시 정의 하는 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE 컨트롤 컨테이너의 대화 상자에 대 한 템플릿을 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 생성 한 `CPaneDialog` 두 단계에서는 개체입니다. 첫째, 코드에서 개체를 생성 합니다. 둘째, 호출 [CPaneDialog::Create](#create)합니다. 올바른 리소스 템플릿 이름 또는 템플릿 ID를 지정 하 고 부모 창에 대 한 포인터를 전달 해야 합니다. 그렇지 않은 경우 만들기 프로세스가 실패합니다. 대화 상자는 WS_CHILD 및 WS_VISIBLE 스타일을 지정 해야 합니다. WS_CLIPCHILDREN 및 WS_CLIPSIBLINGS 스타일 지정 하는 것이 좋습니다. 자세한 내용은 참조 [창 스타일](window-styles.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpanedialog.h  
  
##  <a name="create"></a>CPaneDialog::Create  
 도킹 대화 상자를 만들고 연결 하는 `CPaneDialog` 개체입니다.  
  
```  
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID,  
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

 
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszWindowName`  
 도킹 대화 상자의 이름입니다.  
  
 [in] `pParentWnd`  
 부모 창을 가리킵니다.  
  
 [in] `bHasGripper`  
 `TRUE`캡션 (위치 조정 막대;)를 사용 하 여 도킹 대화 상자를 만들려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `lpszTemplateName`  
 리소스 대화 서식 파일의 이름입니다.  
  
 [in] `nStyle`  
 Windows 스타일입니다.  
  
 [in] `nID`  
 컨트롤 id입니다.  
  
 [in] `nIDTemplate`  
 대화 상자 템플릿 리소스 ID입니다.  
  
 [in] `dwTabbedStyle`  
 사용자가 컨트롤로 끌어 다른 제어판이 컨트롤 창의 캡션에 때 발생 하는 탭된 창의 스타일입니다. 기본값은 `AFX_CBRS_REGULAR_TABS`입니다. 자세한 내용은의 설명 섹션을 참조 하십시오.는 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) 메서드.  
  
 [in] `dwControlBarStyle`  
 추가 스타일 특성입니다. 기본값은 `AFX_DEFAULT_DOCKING_PANE_STYLE`입니다. 자세한 내용은의 설명 섹션을 참조 하십시오.는 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) 메서드.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Create` 에서 메서드는 `CPaneDialog` 클래스입니다. 이 예제는의 일부는 [창 크기 설정 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_SetPaneSize #&2;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize #&3;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>CPaneDialog::HandleInitDialog  
 처리는 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) 메시지입니다.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wParam`  
 기본 키보드 포커스를 받을 수 있는 컨트롤에 대 한 핸들입니다.  
  
 [in] `lParam`  
 추가 초기화 데이터를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다. 또한 `TRUE` 로 지정 된 컨트롤에 키보드 포커스를 설정 된 `wParam` 매개 변수입니다. `FALSE` 방지 기본 키보드 포커스를 설정 합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는이 메서드를 사용 하 여 컨트롤 및 모양의 대화 상자를 초기화 합니다. 프레임 워크 대화 상자를 표시 하기 전에이 메서드를 호출 합니다.  
  
##  <a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo  
 OLE 컨트롤 컨테이너의 대화 상자에 대 한 템플릿을 지정 합니다.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOccDialogInfo`  
 대화 상자 개체를 만드는 데 사용 되는 대화 상자 템플릿에 대 한 포인터입니다. 이 매개 변수 값에 이후에 전달 되는 [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) 메서드.  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지원의 [COccManager](../../mfc/reference/coccmanager-class.md) ActiveX 컨트롤 및 OLE 컨트롤 사이트를 관리 하는 클래스입니다. _AFX_OCC_DIALOG_INFO 구조는 afxocc.h 헤더 파일에 정의 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)   
 [창 스타일](../../mfc/reference/window-styles.md)




