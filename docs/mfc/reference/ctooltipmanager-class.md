---
title: "CTooltipManager 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager class
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3bbf191aacdd318f2afb0bd1a126c3eff290fad6
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipmanager-class"></a>CTooltipManager 클래스
도구 설명에 대한 런타임 정보를 유지합니다. `CTooltipManager` 클래스는 응용 프로그램당 한 번씩 인스턴스화됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤을 만듭니다.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|도구 설명 컨트롤을 삭제합니다.|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤의 시각적 모양을 사용자 지정합니다.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|도구 설명 컨트롤에 대한 텍스트 및 설명을 설정합니다.|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>주의  
 사용 하 여 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, 및 `CTooltipManager` 응용 프로그램에서 사용자 지정된 도구를 구현할 수 있습니다. 이러한 도구 설명 클래스를 사용 하는 방법의 예를 들어 참조는 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) 항목입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtooltipmanager.h  
  
##  <a name="a-namecreatetooltipa--ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 도구 설명 컨트롤을 만듭니다.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `pToolTip`  
 도구 설명 포인터에 대 한 참조입니다. 함수가 반환 될 때 새로 생성된 된 도구 설명을 가리키도록 설정 됩니다.  
  
 [in] `pWndParent`  
 도구 설명의 부모입니다.  
  
 [in] `nType`  
 도구 설명의 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 도구 설명 하는&0;이 아닌 경우 성공적으로 만들어졌습니다.  
  
### <a name="remarks"></a>주의  
 호출 해야 [CTooltipManager::DeleteToolTip](#deletetooltip) 다시 전달 되는 도구 설명 컨트롤을 삭제 하려면 `pToolTip`합니다.  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 도구 설명에 따라 생성 하는 각 도구 설명의 시각적 표시 매개 변수 집합을 입력 하는 `nType` 지정 합니다. 하나 이상의 도구 설명 형식에 대 한 매개 변수를 변경 하려면 호출 [CTooltipManager::SetTooltipParams](#settooltipparams)합니다.  
  
 유효한 도구 설명 유형이 다음 표에 나와 있습니다.  
  
|도구 설명 형식|컨트롤 범주|예제 형식|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|단추입니다.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|캡션 표시줄입니다.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|다른 범주에 맞지 않는 모든 컨트롤입니다.|없음|  
|AFX_TOOLTIP_TYPE_DOCKBAR|도킹 가능한 창입니다.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|텍스트 상자입니다.|없음|  
|AFX_TOOLTIP_TYPE_MINIFRAME|미니 프레임입니다.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|계획 합니다.|없음|  
|AFX_TOOLTIP_TYPE_RIBBON|리본 표시줄입니다.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|탭 컨트롤입니다.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|도구 모음입니다.|CMFCToolBar, CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|도구 상자입니다.|없음|  
  
##  <a name="a-namedeletetooltipa--ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 도구 설명 컨트롤을 삭제합니다.  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `pToolTip`  
 제거할 도구 설명에 대 한 포인터에 대 한 참조입니다.  
  
### <a name="remarks"></a>주의  
 각각에 대해이 메서드를 호출 [CToolTipCtrl 클래스](../../mfc/reference/ctooltipctrl-class.md) 하 여 만들어진 [CTooltipManager::CreateToolTip](#createtooltip)합니다. 부모 컨트롤에서이 메서드를 호출 해야 해당 `OnDestroy` 처리기입니다. 이 프레임 워크에서 도구 설명을 올바르게 제거 해야 합니다. 이 메서드는 설정 `pToolTip` 를 `NULL` 반환 합니다.  
  
##  <a name="a-namesettooltipparamsa--ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 지정 된 Windows 컨트롤 형식에 대 한 도구 설명 컨트롤의 모양을 사용자 지정합니다.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTypes`  
 컨트롤 종류를 지정합니다.  
  
 [in] `pRTC`  
 사용자 지정 도구 설명의 런타임 클래스입니다.  
  
 [in] `pParams`  
 도구 설명 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 런타임 클래스 및 초기 매개 변수는 설정의 [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) 도구 설명을 만들 때 사용 합니다. 컨트롤을 호출 하는 경우 [CTooltipManager::CreateToolTip](#createtooltip) 도구 설명에 전달 하 여 표시 된 형식 중 하나 즉 입력 `nTypes`, 도구 설명 관리자 도구 설명 컨트롤에 지정 된 런타임 클래스의 인스턴스를 만듭니다 `pRTC` 로 지정 된 매개 변수 전달 `pParams` 새 도구 설명에 있습니다.  
  
 이 메서드를 호출 하면 모든 기존 도구 설명 소유자 AFX_WM_UPDATETOOLTIPS 메시지를 수신 하 고 도구 설명을 사용 하 여 다시 만들어야 [CTooltipManager::CreateToolTip](#createtooltip)합니다.  
  
 `nTypes`유효한 도구 설명의 조합 하는 형식 수 [CTooltipManager::CreateToolTip](#createtooltip) 사용 되거나 AFX_TOOLTIP_TYPE_ALL 될 수 있습니다. AFX_TOOLTIP_TYPE_ALL를 전달 하는 경우 모든 도구 설명 형식이 영향을 받습니다.  
  
### <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `SetTooltipParams` 의 메서드는 `CTooltipManager` 클래스입니다. 이 코드 조각은의 일부인는 [그리기 클라이언트 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DrawClient #&11;](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="a-namesettooltiptexta--ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
 텍스트를 설정 하는 도구 설명에 대 한 설명입니다.  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTI`  
 TOOLINFO 개체에 대 한 포인터입니다.  
  
 [in, out] `pToolTip`  
 텍스트 및 설명을 설정할 수 있는 도구 설명 컨트롤에 대 한 포인터입니다.  
  
 [in] `nType`  
 이 도구 설명과 연결 된 컨트롤의 유형을 지정 합니다.  
  
 [in] `strText`  
 텍스트 도구 설명 텍스트로 설정입니다.  
  
 [in] `lpszDescr`  
 도구 설명에 대 한 포인터입니다. 수 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 값 `nType` 와 같은 값 이어야 합니다는 `nType` 의 매개 변수 [CTooltipManager::CreateToolTip](#createtooltip) 도구 설명을 만들 때.  
  
##  <a name="a-nameupdatetooltipsa--ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md)

