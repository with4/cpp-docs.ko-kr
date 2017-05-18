---
title: "CMFCDropDownToolBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolBar class
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ba643d67b12ba22bcf9fb54d32f3c329fa2c65a0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar 클래스
사용자가 최상위 도구 모음 단추를 누르고 있을 때 나타나는 도구 모음입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu`를 재정의합니다.)|  
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(재정의 [CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|  
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(재정의 [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|  
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||  
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||  
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(`CMFCToolBar::OnSendCommand`를 재정의합니다.)|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(재정의 [CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/571a38ab-2a56-4968-9796-273516126f80).)|  
  
### <a name="remarks"></a>주의  
 A `CMFCDropDownToolBar` 개체를 결합 하는 도구 모음의 시각적 모양을 팝업 메뉴의 동작입니다. 때 사용자를 누르고 드롭다운 도구 모음 단추 (참조 [CMFCDropDownToolbarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), 드롭다운 도구 모음이 나타납니다 및 사용자를 스크롤하여 마우스 단추를 놓으면 드롭다운 도구 모음에서 단추에 선택할 수 있습니다. 사용자가 드롭다운 도구 모음에서 단추를 선택한 후 최상위 도구 모음에는 현재 단추와 해당 단추가 표시 됩니다.  
  
 드롭다운 도구 모음 사용자 지정 또는 도킹 수 없고를 분리 한 상태로 필요가 없습니다.  
  
 다음 그림에 표시 된 `CMFCDropDownToolBar` 개체:  
  
 ![CMFCDropDownToolbar의 예제](../../mfc/reference/media/cmfcdropdown.png "cmfcdropdown")  
  
 만들는 `CMFCDropDownToolBar` 는 일반 도구 모음을 만들면 같은 방식으로 개체 (참조 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)).  
  
 부모 도구 모음에 드롭다운 도구 모음을 삽입 합니다.  
  
 1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.  
  
 2. 만들기는 `CMFCDropDownToolBarButton` 드롭다운 도구 모음을 포함 하는 개체 (자세한 내용은 참조 [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).  
  
 3. 대체 되는 더미 단추는 `CMFCDropDownToolBarButton` 개체를 사용 하 여 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)합니다.  
  
 도구 모음 단추에 대 한 자세한 내용은 참조 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다. 드롭다운 도구 모음의 예를 들어 VisualStudioDemo 샘플 프로젝트를 참조 하십시오.  
  
## <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `Create` 에서 메서드는 `CMFCDropDownToolBar` 클래스입니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&29;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&30;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdropdowntoolbar.h  
  
##  <a name="allowshowonpanemenu"></a>CMFCDropDownToolBar::AllowShowOnPaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="loadbitmap"></a>CMFCDropDownToolBar::LoadBitmap  
 응용 프로그램 리소스에서 도구 모음 이미지를 로드합니다.  
  
```  
virtual BOOL LoadBitmap(
    UINT uiResID,  
    UINT uiColdResID=0,  
    UINT uiMenuResID=0,  
    BOOL bLocked=FALSE,  
    UINT uiDisabledResID=0,  
    UINT uiMenuDisabledResID=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiResID`  
 핫 도구 모음 이미지를 참조하는 비트맵의 리소스 ID입니다.  
  
 [in] `uiColdResID`  
 콜드 도구 모음 이미지를 참조하는 비트맵의 리소스 ID입니다.  
  
 [in] `uiMenuResID`  
 일반 메뉴 이미지를 참조하는 비트맵의 리소스 ID입니다.  
  
 [in] `bLocked`  
 `TRUE`도구 모음의 잠그려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `uiDisabledResID`  
 비활성화된 도구 모음 이미지를 참조하는 비트맵의 리소스 ID입니다.  
  
 [in] `uiMenuDisabledResID`  
 비활성화된 메뉴 이미지를 참조하는 비트맵의 리소스 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공하면 0이 아니고, 실패하면 0입니다.  
  
### <a name="remarks"></a>주의  
 [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) 메서드 도구 모음에 연관 된 이미지를 로드 하려면이 메서드를 호출 합니다. 이미지 리소스의 사용자 지정 로드를 수행하려면 이 메서드를 재정의합니다.  
  
 `LoadBitmapEx` 메서드를 호출하여 도구 모음을 만든 후 추가 이미지를 로드합니다.  
  
##  <a name="loadtoolbar"></a>CMFCDropDownToolBar::LoadToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadToolBar(
    UINT uiResID,  
    UINT uiColdResID = 0,  
    UINT uiMenuResID = 0,
    BOOL = FALSE,  
    UINT uiDisabledResID = 0,  
    UINT uiMenuDisabledResID = 0,  
    UINT uiHotResID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiResID`  
 [in] `uiColdResID`  
 [in] `uiMenuResID`  
 [in] `BOOL`  
 [in] `uiDisabledResID`  
 [in] `uiMenuDisabledResID`  
 [in] `uiHotResID`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onlbuttonup"></a>CMFCDropDownToolBar::OnLButtonUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlags`  
 [in] `point`  
  
### <a name="remarks"></a>주의  
  
##  <a name="onmousemove"></a>CMFCDropDownToolBar::OnMouseMove  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nFlags`  
 [in] `point`  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsendcommand"></a>CMFCDropDownToolBar::OnSendCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pButton`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onupdatecmdui"></a>CMFCDropDownToolBar::OnUpdateCmdUI  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [CMFCDropDownToolbarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)




