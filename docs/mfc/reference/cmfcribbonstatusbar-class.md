---
title: "CMFCRibbonStatusBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBar class
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
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
ms.openlocfilehash: 8fc2ec14c3f6320f45128bf36824ce7f9b8de9c5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar 클래스
`CMFCRibbonStatusBar` 클래스는 리본 요소를 표시할 수 있는 상태 표시줄 컨트롤을 구현 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|리본 메뉴 상태 표시줄에 동적 요소를 추가 합니다.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|리본 메뉴 상태 표시줄에 새 리본 요소를 추가합니다.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|리본 메뉴 상태 표시줄의 확장된 된 영역에는 리본 요소를 추가합니다.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|리본 메뉴 상태 표시줄에는 구분 기호를 추가합니다.|  
|[CMFCRibbonStatusBar::Create](#create)|리본 메뉴 상태 표시줄을 만듭니다.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|확장된 스타일으로 리본 메뉴 상태 표시줄을 만듭니다.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|지정 된 명령 ID를 가진 요소에 대 한 포인터를 반환|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|리본 메뉴 상태 표시줄의 주 영역에 있는 요소의 수를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|지정된 된 인덱스에 있는 요소에 대 한 포인터를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|리본 메뉴 상태 표시줄의 확장된 된 영역에 있는 요소의 수를 반환 합니다.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|리본 메뉴 상태 표시줄에서 확장된 영역의 지정한 인덱스에 있는 요소에 대한 포인터를 반환합니다.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|리본 메뉴 상태 표시줄 정보 모드 사용 하는지 여부를 결정 합니다.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(재정의 [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|리본 메뉴 상태 표시줄에서 모든 요소를 제거합니다.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|리본 메뉴 상태 표시줄에서 지정 된 명령 ID를 가진 요소를 제거 합니다.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|사용 하거나 리본 메뉴 상태 표시줄에 대 한 정보 모드를 해제 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|리본 메뉴 상태 표시줄 정보 모드를 사용 하는 경우에 표시 되는 정보 문자열을 표시 합니다.|  
  
## <a name="remarks"></a>주의  
 리본 메뉴 상태 표시줄에 대 한 기본 제공 상황에 맞는 메뉴를 사용 하 여 리본 메뉴 상태 표시줄에 리본 요소의 표시 유형을 변경할 수 있습니다. 추가 하거나 요소를 동적으로 제거할 수 있습니다.  
  
 리본 메뉴 상태 표시줄에 두 개의 영역: 주 영역 및 확장 된 영역입니다. 확장된 된 영역 리본 메뉴 상태 표시줄의 오른쪽에 표시 되 고 주 영역 보다는 다른 색으로 나타납니다.  
  
 일반적으로 상태 표시줄의 주 영역 상태 알림을 표시 하 고 확장된 된 영역 뷰 컨트롤을 표시 합니다. 사용자가 리본 메뉴 상태 표시줄에서 크기 조정 확장된 된 영역 최대한 오랫동안 표시 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCRibbonStatusBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 리본 메뉴 상태 표시줄에 새 리본 요소를 추가, 리본 메뉴 상태 표시줄의 확장된 된 영역에는 리본 요소를 추가 하는 방법을 보여 주는 예제는 한 구분 기호를 추가, 하 고 리본 메뉴 상태 표시줄에 대 한 일반 모드를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&15;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp #&16;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonstatusbar.h  
  
##  <a name="adddynamicelement"></a>CMFCRibbonStatusBar::AddDynamicElement  
 리본 메뉴 상태 표시줄에 동적 요소를 추가 합니다.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pElement`  
 동적 요소에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 일반 요소와는 달리 동적 요소를 사용자 지정할 수 없는 경우 및 사용자 지정 메뉴 상태 표시줄의 표시 하지는 않습니다.  
  
##  <a name="addelement"></a>CMFCRibbonStatusBar::AddElement  
 리본 메뉴 상태 표시줄에 새 리본 요소를 추가합니다.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pElement`  
 추가 된 요소에 대 한 포인터입니다.  
  
 [in] `lpszLabel`  
 요소의 텍스트 레이블입니다.  
  
 [in] `bIsVisible`  
 `TRUE`표시로 요소를 추가 하려는 경우 `FALSE` 으로 요소를 추가 하려는 경우 숨겨집니다.  
  
##  <a name="addextendedelement"></a>CMFCRibbonStatusBar::AddExtendedElement  
 리본 메뉴 상태 표시줄의 확장된 된 영역에는 리본 요소를 추가합니다.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pElement`  
 추가 된 요소에 대 한 포인터입니다.  
  
 [in] `lpszLabel`  
 요소의 텍스트 레이블입니다.  
  
 [in] `bIsVisible`  
 `TRUE`표시로 요소를 추가 하려는 경우 `FALSE` 으로 요소를 추가 하려는 경우 숨겨집니다.  
  
### <a name="remarks"></a>주의  
 확장된 영역은 상태 표시줄 컨트롤의 오른쪽에 있습니다.  
  
##  <a name="addseparator"></a>CMFCRibbonStatusBar::AddSeparator  
 리본 메뉴 상태 표시줄에는 구분 기호를 추가합니다.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>주의  
 메서드 뒤 구분 기호를 추가 하는 프레임 워크 [CMFCRibbonStatusBar::AddElement](#addelement)합니다. 마지막 요소를 삽입합니다.  
  
##  <a name="create"></a>CMFCRibbonStatusBar::Create  
 리본 메뉴 상태 표시줄을 만듭니다.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 부모 창에 대 한 포인터입니다.  
  
 [in] `dwStyle`  
 컨트롤 스타일의 논리 OR 조합입니다.  
  
 [in] `nID`  
 상태 표시줄의 컨트롤 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`상태 표시줄을 성공적으로 만들어지면 `FALSE` 그렇지 않은 경우.  
  
##  <a name="createex"></a>CMFCRibbonStatusBar::CreateEx  
 확장된 스타일을 가진 리본 메뉴 상태 표시줄을 만듭니다.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentWnd`  
 부모 창에 대 한 포인터입니다.  
  
 `dwCtrlStyle`  
 상태 표시줄 개체를 만들기 위한 추가 스타일의 논리 OR 조합입니다.  
  
 `dwStyle`  
 상태 표시줄의 컨트롤 스타일입니다.  
  
 `nID`  
 상태 표시줄의 컨트롤 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`상태 표시줄을 성공적으로 만들어지면 `FALSE` 그렇지 않은 경우.  
  
##  <a name="findbyid"></a>CMFCRibbonStatusBar::FindByID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiCmdID`  
 [in] `BOOL`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="findelement"></a>CMFCRibbonStatusBar::FindElement  
 지정 된 명령 ID를 가진 요소에 대 한 포인터를 반환  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 요소의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 명령 ID를 가진 요소에 대 한 포인터 `NULL`이러한 요소가 없는 경우.  
  
##  <a name="getcount"></a>CMFCRibbonStatusBar::GetCount  
 리본 메뉴 상태 표시줄의 주 영역에 있는 요소의 수를 반환 합니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 메뉴 상태 표시줄의 주 영역에 있는 요소의 수입니다.  
  
##  <a name="getelement"></a>CMFCRibbonStatusBar::GetElement  
 지정된 된 인덱스에 있는 요소에 대 한 포인터를 반환 합니다.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 상태 표시줄 컨트롤의 기본 영역에 있는 요소의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 인덱스에 있는 요소에 대 한 포인터입니다. `NULL`인덱스가 있는 경우에 음수 또는 상태 표시줄에 있는 요소의 수를 초과 합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getexcount"></a>CMFCRibbonStatusBar::GetExCount  
 리본 메뉴 상태 표시줄의 확장된 된 영역에 있는 요소의 수를 반환 합니다.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리본 메뉴 상태 표시줄의 확장된 된 영역에 있는 요소의 수입니다.  
  
##  <a name="getexelement"></a>CMFCRibbonStatusBar::GetExElement  
 리본 메뉴 상태 표시줄에서 확장된 영역의 지정한 인덱스에 있는 요소에 대한 포인터를 반환합니다. 확장된 영역은 상태 표시줄 컨트롤의 오른쪽에 있습니다.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 상태 표시줄 컨트롤의 확장된 영역에 있는 요소의&0;부터 시작하는 인덱스를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 리본 메뉴 상태 표시줄에서 확장된 영역의 지정한 인덱스에 있는 요소에 대한 포인터입니다. `NULL`가 음수이거나 리본 메뉴 상태 표시줄의 확장된 영역에 있는 요소 수를 초과하는 경우 `nIndex`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getextendedarea"></a>CMFCRibbonStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getspace"></a>CMFCRibbonStatusBar::GetSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="isbottomframe"></a>CMFCRibbonStatusBar::IsBottomFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="isextendedelement"></a>CMFCRibbonStatusBar::IsExtendedElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pElement`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="isinformationmode"></a>CMFCRibbonStatusBar::IsInformationMode  
 리본 메뉴 상태 표시줄 정보 모드 사용 하는지 여부를 결정 합니다.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`상태 표시줄 정보 모드;에서 작업 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 정보 모드에서 상태 표시줄은 모든 일반 창 숨깁니다 메시지 문자열을 표시 합니다.  
  
##  <a name="ondrawinformation"></a>CMFCRibbonStatusBar::OnDrawInformation  
 리본 메뉴 상태 표시줄 정보 모드를 사용 하는 경우에 표시 되는 문자열을 표시 합니다.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `strInfo`  
 정보 문자열입니다.  
  
 [in] `rectInfo`  
 경계 사각형입니다.  
  
### <a name="remarks"></a>주의  
 상태 표시줄에 정보 문자열의 모양을 사용자 지정 하려는 경우에 파생된 클래스에서이 메서드를 재정의 합니다. 사용 하 여는 [CMFCRibbonStatusBar::SetInformation](#setinformation) 메서드를 상태 표시줄 정보 모드로 전환 합니다. 이 모드에서는 상태 표시줄 모든 창 숨겨지고로 지정 된 정보 문자열을 표시 `strInfo`합니다.  
  
##  <a name="recalclayout"></a>CMFCRibbonStatusBar::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="removeall"></a>CMFCRibbonStatusBar::RemoveAll  
 리본 메뉴 상태 표시줄에서 모든 요소를 제거합니다.  
  
```  
void RemoveAll();
```  
  
##  <a name="removeelement"></a>CMFCRibbonStatusBar::RemoveElement  
 리본 메뉴 상태 표시줄에서 지정 된 명령 ID를 가진 요소를 제거 합니다.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiID`  
 상태 표시줄에서 제거할 요소의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정 된 요소가 `uiID` 제거 됩니다. 그렇지 않으면 `FALSE`입니다.  
  
##  <a name="setinformation"></a>CMFCRibbonStatusBar::SetInformation  
 사용 하거나 리본 메뉴 상태 표시줄에 대 한 정보 모드를 해제 합니다.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszInfo`  
 정보 문자열입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 상태 표시줄 정보 모드로 전환 합니다. 이 모드에서는 상태 표시줄 모든 창 숨겨지고로 지정 된 정보 문자열을 표시 `lpszInfo`합니다.  
  
 LpszInfo 경우 `NULL`, 상태 표시줄을 일반 모드로 되돌립니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)

