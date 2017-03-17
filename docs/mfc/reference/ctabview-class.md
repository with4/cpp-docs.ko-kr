---
title: "CTabView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
dev_langs:
- C++
helpviewer_keywords:
- CTabView class
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 20f5745c3784e771d6ec95f7d4dc363142c687f8
ms.lasthandoff: 02/24/2017

---
# <a name="ctabview-class"></a>CTabView 클래스
`CTabView` 탭 컨트롤 클래스의 사용을 간소화 하는 클래스 ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md))에서 MFC의 문서/뷰 아키텍처를 사용 하는 응용 프로그램입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|탭 컨트롤에 새 보기를 추가합니다.|  
|[CTabView::FindTab](#findtab)|탭 컨트롤의 지정된 된 보기의 인덱스를 반환합니다.|  
|[CTabView::GetActiveView](#getactiveview)|현재 활성 보기에 대 한 포인터를 반환합니다.|  
|[CTabView::GetTabControl](#gettabcontrol)|뷰와 연결 된 탭 컨트롤에 대 한 참조를 반환 합니다.|  
|[CTabView::RemoveView](#removeview)|탭 컨트롤에서 뷰를 제거합니다.|  
|[CTabView::SetActiveView](#setactiveview)|뷰를 활성 상태로 만듭니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|탭 보기 공유 가로 스크롤 막대를 갖는지 확인 탭 보기를 만들 때에 프레임 워크에서 호출 합니다.|  
|[CTabView::OnActivateView](#onactivateview)|활성 또는 비활성 탭 보기 만들어질 때 프레임 워크에 의해 호출 됩니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스를 사용 하는 문서/뷰 응용 프로그램에 탭된 보기를 적용할 쉽게 합니다. `CTabView`한 `CView`-포함 된 포함 된 클래스를 파생 `CMFCTabCtrl` 개체입니다. `CTabView`지 원하는 데 필요한 모든 메시지를 처리 하는 `CMFCTabCtrl` 개체입니다. 클래스 파생 시키기만 `CTabView` 응용 프로그램에 연결 하 고 다음 추가 `CView`-를 사용 하 여 파생 클래스는 `AddView` 메서드. 탭 컨트롤에 탭으로 이러한 뷰를 표시 됩니다.  
  
 예를 들어, 다른 방법으로 표현할 수 있는 문서를 할 수 있습니다: 스프레드시트, 차트, 편집 가능한 폼 및 등으로 합니다. 필요에 따라 데이터를 그리기 개별 보기를 만들 수 있으며, 삽입 프로그램 `CTabView`-개체를 파생 하 고 추가 코딩 없이도 탭 합니다.  
  
 [TabbedView 샘플: MFC 탭 보기 응용 프로그램](../../visual-cpp-samples.md) 의 사용법을 보여 줍니다 `CTabView`합니다.  
  
## <a name="example"></a>예제  
 다음 예제와 어떻게 `CTabView` TabbedView 샘플에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_TabbedView #&1;](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxTabView.h  
  
##  <a name="addview"></a>CTabView::AddView  
 탭 컨트롤에 뷰를 추가합니다.  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pViewClass`  
 삽입 된 보기의 런타임 클래스에 대 한 포인터입니다.  
  
 [in] `strViewLabel`  
 탭의 텍스트를 지정합니다.  
  
 [in] `iIndex`  
 보기를 삽입 하는&0;부터 시작 하는 위치를 지정 합니다. 위치가-1 이면 새 탭 끝에 삽입 됩니다.  
  
 [in] `pContext`  
 에 대 한 포인터는 `CCreateContext` 보기.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 뷰의 인덱스입니다. 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 프레임에 포함 된 탭 컨트롤에 뷰를 추가 하려면이 함수를 호출 합니다.  
  
##  <a name="findtab"></a>CTabView::FindTab  
 탭 컨트롤의 지정된 된 보기의 인덱스를 반환합니다.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hWndView`  
 보기의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 경우 뷰의 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 에 지정 된 핸들이 뷰의 인덱스를 검색 하려면이 함수를 호출 합니다.  
  
##  <a name="getactiveview"></a>CTabView::GetActiveView  
 현재 활성 보기에 대 한 포인터를 반환합니다.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 보기에 대 한 유효한 포인터 또는 `NULL` 활성 뷰가 없는 경우.  
  
### <a name="remarks"></a>주의  
  
##  <a name="gettabcontrol"></a>CTabView::GetTabControl  
 뷰와 연결 된 탭 컨트롤에 대 한 참조를 반환 합니다.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>반환 값  
 뷰와 연결 된 탭 컨트롤에 대 한 참조입니다.  
  
##  <a name="isscrollbar"></a>CTabView::IsScrollBar  
 탭 보기 공유 가로 스크롤 막대를 갖는지 확인 탭 보기를 만들 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`공유 스크롤 막대를 함께 탭 보기를 만들어야 합니다. 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 호출 하는 프레임 워크 때는 `CTabView` 개체가 만들어집니다.  
  
 재정의 `IsScrollBar` 에서 메서드는 `CTabView`-파생 클래스와 반환 `TRUE` 공유 가로 스크롤 막대에 있는 뷰를 만들려는 경우입니다.  
  
##  <a name="onactivateview"></a>CTabView::OnActivateView  
 활성 또는 비활성 탭 보기 만들어질 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `view`  
 보기에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행하지 않습니다. 이 메서드를 재정의 하는 `CTabView`-이 알림을 처리 하는 클래스를 파생 합니다.  
  
##  <a name="removeview"></a>CTabView::RemoveView  
 탭 컨트롤에서 뷰를 제거합니다.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iTabNum`  
 제거할 보기의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 제거한 뷰의 인덱스입니다. 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="setactiveview"></a>CTabView::SetActiveView  
 뷰를 활성 상태로 만듭니다.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iTabNum`  
 탭 보기의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정된 된 보기 활성 상태인 경우 `FALSE` 경우 보기의 인덱스가 잘못 되었습니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)

