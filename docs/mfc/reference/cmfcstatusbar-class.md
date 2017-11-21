---
title: "CMFCStatusBar 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs: C++
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 734097d8fffcbe21f17b68432d6233a03b11a28a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar 클래스
`CMFCStatusBar` 비슷한 상태 표시줄을 구현 하는 클래스는 `CStatusBar` 클래스입니다. 그러나 `CMFCStatusBar` 클래스에는 `CStatusBar` 클래스에 의해 제공되지 않는 기능(예: 이미지, 애니메이션 및 진행률 표시줄을 표시하는 기능 및 마우스 두 번 클릭에 응답하는 기능)이 포함되어 있습니다. 

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>구문  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|컨트롤 막대를 만들고 연결 하는 [CPane](../../mfc/reference/cpane-class.md) 개체입니다. (재정의 [cpane:: Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|컨트롤 막대를 만들고 연결 하는 [CPane](../../mfc/reference/cpane-class.md) 개체입니다. (재정의 [cpane:: Createex](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|이 창 및 부모 프레임 간에 다른 창을 동적으로 삽입할 수 있는지 여부를 결정 합니다. (재정의 [:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|사용 가능 / 불가능 마우스의 처리 상태 표시줄에 두 번 클릭 합니다.|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|지정 된 창에서 진행률 표시줄을 표시 합니다.|  
|[CMFCStatusBar::GetCount](#getcount)|상태 표시줄에 창 수를 반환합니다.|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|창 스타일을 반환합니다. (재정의 [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|상태 표시줄의 지정 된 창을 픽셀 단위로 너비를 반환합니다.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|상태 표시줄의 지정 된 창에 대 한 도구 설명 텍스트를 반환합니다.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|지정 된 창을 무효화 하 고 해당 콘텐츠를 다시 그립니다.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|이에 연결 된 Windows 창을 만들기 전에 프레임 워크에서 호출 `CWnd` 개체입니다. (재정의 [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|지정한 창에 애니메이션을 할당합니다.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|상태 표시줄의 지정 된 창에 대 한 배경색을 설정합니다.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|상태 표시줄의 지정 된 창에 대 한 표시기 아이콘을 설정합니다.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|상태 표시줄의 지정 된 창에 대 한 진행률 표시줄의 현재 진행 상태를 설정합니다.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|창 스타일을 설정합니다. (재정의 [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|상태 표시줄의 지정 된 창에 대 한 텍스트 색을 설정합니다.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|상태 표시줄의 지정 된 창 픽셀 너비를 설정 합니다.|  
|[CMFCStatusBar::SetTipText](#settiptext)|상태 표시줄의 지정 된 창에 대 한 도구 설명 텍스트를 설정합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|창 상태 표시줄을 다시 그리면 때 프레임 워크에서 호출 됩니다.|  
  
## <a name="remarks"></a>설명  
 다음 그림에서 상태 표시줄의 그림 [상태 표시줄 데모 샘플](../../visual-cpp-samples.md) 응용 프로그램입니다.  
  
 ![CMFCStatusBar의 예제](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")  
  
## <a name="example"></a>예제  
 다음 예제에서는 다양 한 메서드를 호출 하는 응용 프로그램이 사용 하는 지역 변수는 `CMFCStatusBar` 클래스입니다. 이러한 변수는 StatusBarDemoView.h에서 선언 됩니다. 주 프레임 MainFrm.h에 선언 된, 문서 StatusBarDemoDoc.h에 선언 된 및 보기 StatusBarDemoView.h에서 선언 됩니다. 이 코드 조각은의 일부인는 [상태 표시줄 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 참조를 가져오는 방법을 `CMFCStatusBar` 도입 하 여 개체는 `GetStatusBar` MainFrm.h에서이 메서드를 호출한 다음의 방법으로는 `GetStatusBar` StatusBarDemoView.h에서 메서드. 이 코드 조각은의 일부인는 [상태 표시줄 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 다양 한 메서드를 호출 하는 `CMFCStatusBar` StatusBarDemoView.cpp의 클래스. 상수는 MainFrm.h에도 선언 됩니다. 이 예제에서는 설정 아이콘, 상태 표시줄 창의 도구 설명 텍스트를 설정, 지정 된 창에서 진행률 표시줄을 표시, 지정 된 창에 애니메이션을 할당, 텍스트 및 상태 표시줄 창의 너비 설정 및는 progr의 현재 진행률 표시기를 설정 하는 방법을 보여 줍니다. 상태 표시줄 창에 대 한 ess 막대입니다. 이 코드 조각은의 일부인는 [상태 표시줄 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="commandtoindex"></a>CMFCStatusBar::CommandToIndex  

  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIDFind`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="create"></a>CMFCStatusBar::Create  

  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="createex"></a>CMFCStatusBar::CreateEx  

  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentWnd`  
 [in] `dwCtrlStyle`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick  
 사용 가능 / 불가능 마우스의 처리 상태 표시줄에 두 번 클릭 합니다.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 경우 `TRUE`, 사용 하도록 설정 하는 마우스의 처리를 두 번 클릭 합니다. 그렇지 않으면 마우스 두 번 클릭 처리 되지 않도록 합니다.  
  
### <a name="remarks"></a>설명  
 두 번 클릭을 처리 하는 상태 표시줄을 사용 하는 경우 Windows 보냅니다는 `WM_COMMAND` 소유자에 게 리소스 ID와 함께 상태에서 사용자 상태 표시줄 창 두 번 클릭할 때마다 표시줄의 알림입니다.  
  
##  <a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar  
 지정한 창에 진행률 표시줄을 표시 합니다.  
  
```  
void EnablePaneProgressBar(
    int nIndex,  
    long nTotal=100,  
    BOOL bDisplayText=FALSE,  
    COLORREF clrBar=-1,  
    COLORREF clrBarDest=-1,  
    COLORREF clrProgressText=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 사용할 수 있도록 해당 진행률 표시줄 창 인덱스를 지정 합니다.  
  
 [in] `nTotal`  
 진행률 표시줄에 대 한 최대값을 지정 합니다.  
  
 [in] `bDisplayText`  
 진행률 표시줄 현재 진행률 값을 표시할지 여부를 지정 합니다.  
  
 [in] `clrBar`  
 진행률 표시줄의 배경색을 지정 합니다.  
  
 [in] `clrBarDest`  
 진행률 표시줄 배경 보조 색을 지정합니다. 다른 값을 사용 하 여 `clrBar` 을 그라데이션에 혼합 색으로 채웁니다.  
  
 [in] `clrProgressText`  
 진행률 표시줄의 텍스트 색을 지정합니다.  
  
### <a name="remarks"></a>설명  
 진행률 표시줄 호출을 사용 하지 않도록 설정 하려는 경우 `EnablePaneProgressBar` 와 `nTotal` -1로 설정 합니다. 기본적으로 `nTotal` 100으로 설정 됩니다. 따라서 백분율로 진행률을 표시 하려면 모든 추가 계산 필요 하지 않습니다.  
  
 에 대 한 다른 값을 전달 해야 `clrBar` 및 `clrBarDest` 진행률 표시줄의 배경색에 색 그라데이션을에 혼합 표시 되도록 합니다. 입니다.  
  
 현재 진행 상태를 설정 하려면 호출는 [CMFCStatusBar::SetPaneProgress](#setpaneprogress) 메서드.  
  
##  <a name="getcount"></a>CMFCStatusBar::GetCount  
 상태 표시줄의 창 수를 검색합니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태 표시줄의 창 수를 지정 합니다.  
  
##  <a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea  

  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea  

  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getitemid"></a>CMFCStatusBar::GetItemID  

  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getitemrect"></a>CMFCStatusBar::GetItemRect  

  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 [in] `lpRect`  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo  

  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpaneprogress"></a>CMFCStatusBar::GetPaneProgress  

  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle  

  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpanetext"></a>CMFCStatusBar::GetPaneText  

  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 [in] `s`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth  
 상태 표시줄 창의 너비를 검색합니다.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 상태 표시줄 창의 인덱스를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 상태 표시줄 창의 너비를 `nIndex` 를 지정 합니다. 그렇지 않은 경우 상태 표시줄 창 존재 하지 않는 경우 0입니다.  
  
##  <a name="gettiptext"></a>CMFCStatusBar::GetTipText  
 상태 표시줄 창의 도구 설명 텍스트를 검색 합니다.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 창에 도구 설명 텍스트를 검색 하려는 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 상태 표시줄 창의 도구 설명 텍스트는 `nIndex` 지정 합니다. 지정 된 상태 표시줄 창이 없는 경우 빈 문자열 하는 그렇지 않은 경우 `nIndex` 이거나 도구 설명 텍스트는 비어 있습니다.  
  
##  <a name="invalidatepanecontent"></a>CMFCStatusBar::InvalidatePaneContent  
 상태 표시줄 창을 무효화 하 고 해당 콘텐츠를 다시 그립니다.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 해당 콘텐츠를 무효화 하 고 다시 그릴를 창의 인덱스를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 상태 표시줄 무효화 될 때 다시 그리기 위한 표시 됩니다. Windows 다시 그려서 때는 `UpdateWindow` 메서드 보냅니다는 `WM_PAINT` 에 메시지는 `OnPaint` 메서드.  
  
##  <a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane  
 상태 표시줄 창 다시 그립니다.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 그리기에 대 한 장치 컨텍스트 포인터입니다.  
  
 [in] `pPane`  
 에 대 한 포인터는 `CMFCStatusBarPaneInfo` 그려야 하는 창에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `OnDrawPane` 장치 컨텍스트를 사용 하 여 창에서을 다시 그리면 `pDC` 의 창 스타일 및 내용에 따라 합니다.  
  
 이 메서드를 재정의 한 `CMFCStatusBar`-창의 모양을 사용자 지정 하는 클래스를 파생 합니다.  
  
##  <a name="precreatewindow"></a>CMFCStatusBar::PreCreateWindow  

  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `cs`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea  

  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setindicators"></a>CMFCStatusBar::SetIndicators  

  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpIDArray`  
 [in] `nIDCount`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimation  
 지정한 창에 애니메이션을 할당합니다.  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 애니메이션을 할당 하려는 창의 인덱스를 지정 합니다.  
  
 [in] `hImageList`  
 애니메이션 프레임을 보유 하는 이미지 목록에 대 한 핸들을 지정 합니다.  
  
 [in] `nFrameRate`  
 애니메이션에 대 한 밀리초 프레임 속도 지정합니다.  
  
 [in] `bUpdate`  
 경우 `TRUE`, 창 콘텐츠를 즉시 업데이트 합니다. 그렇지 않으면 창 콘텐츠 무효화 될 때 업데이트 됩니다.  
  
### <a name="remarks"></a>설명  
 현재 애니메이션을 사용 하지 않도록 설정 하려는 경우 호출 `SetPaneAnimation` 와 `hImageList` 로 설정 `NULL`합니다.  
  
##  <a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor  
 상태 표시줄 창의 배경색을 설정합니다.  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 창에 새 배경 색을 설정 하는 인덱스를 지정 합니다.  
  
 [in] `clrBackground`  
 새 배경 색을 지정합니다.  
  
 [in] `bUpdate`  
 경우 `TRUE`, 창 콘텐츠를 즉시 업데이트 합니다. 그렇지 않은 경우 다른 방법으로 창에서 무효화 될 때까지 창 콘텐츠를 업데이트 하지 마십시오.  
  
##  <a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon  
 상태 표시줄 창의 아이콘을 설정 합니다.  
  
```  
void SetPaneIcon(
    int nIndex,  
    HICON hIcon,  
    BOOL bUpdate=TRUE);

 
void SetPaneIcon(
    int nIndex,  
    HBITMAP hBmp,  
    COLORREF clrTransparent=RGB(255, 0, 255),  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 창에 이미지를 설정 하는 인덱스를 지정 합니다.  
  
 [in] `hIcon`  
 창 이미지도 설정할 수 있는 아이콘에 대 한 핸들을 지정 합니다.  
  
 [in] `bUpdate`  
 창 콘텐츠를 즉시 업데이트할 것인지 지정 합니다.  
  
 [in] `hBmp`  
 창 이미지도 설정 하도록 비트맵에 대 한 핸들을 지정 합니다.  
  
 [in] `clrTransparent`  
 투명 한 비트맵의 색을 지정 하는 `hBmp` 나타냅니다.  
  
### <a name="remarks"></a>설명  
 전달할 수 있습니다 `HICON` 또는 `HBITMAP` 창의 이미지를 설정 하는 투명 한 색과 함께 합니다. 이미지를 더 이상 표시 하지 않을 경우 전달 된 `NULL` 이미지 핸들로 값입니다.  
  
 모든 실행 중인 애니메이션이 없는 경우는 [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) 가 설정, 애니메이션이 중지 됩니다.  
  
##  <a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo  

  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setpaneprogress"></a>CMFCStatusBar::SetPaneProgress  
 지정 된 창에 대 한 진행률 표시줄의 현재 진행률 표시기를 설정 합니다.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 창에 진행률 표시기를 업데이트 하려는 인덱스를 지정 합니다.  
  
 [in] `nCurr`  
 진행률 표시기의 현재 값을 지정합니다.  
  
 [in] `bUpdate`  
 창에서 즉시 업데이트할 수 있는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 지정 된 창에서 진행률 표시줄에 대 한 진행률 표시기를 업데이트 하려는 경우이 메서드를 호출 합니다.  
  
 지정 된 창에 대 한이 함수를 사용 하려면 호출 해야 [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) 첫 번째입니다.  
  
##  <a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle  

  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 [in] `nStyle`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setpanetext"></a>CMFCStatusBar::SetPaneText  

  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 [in] `lpszNewText`  
 [in] `bUpdate`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor  
 지정 된 창의 텍스트 색을 설정합니다.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 새 텍스트 색을 할당 하려면 창의 인덱스를 지정 합니다.  
  
 [in] `clrText`  
 텍스트 색을 지정 합니다.  
  
 [in] `bUpdate`  
 경우 `TRUE`, 창 콘텐츠를 즉시 업데이트 합니다. 그렇지 않은 경우 다른 방법으로 창에서 무효화 될 때까지 창 콘텐츠를 업데이트 하지 마십시오.  
  
##  <a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth  
 상태 표시줄 창의 너비를 설정 합니다.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 상태 표시줄 창의 새 너비를 설정할 인덱스입니다.  
  
 [in] `cx`  
 픽셀 단위로 상태 표시줄 창의 새 너비입니다.  
  
##  <a name="settiptext"></a>CMFCStatusBar::SetTipText  
 상태 표시줄 창의 도구 설명 텍스트를 설정 합니다.  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 도구 설명 텍스트를 할당 하려면 창의 인덱스입니다.  
  
 [in] `pszTipText`  
 새 도구 설명 텍스트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane 클래스](../../mfc/reference/cpane-class.md)   
 [CStatusBar 클래스](../../mfc/reference/cstatusbar-class.md)
