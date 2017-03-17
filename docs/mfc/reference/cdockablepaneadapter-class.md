---
title: "CDockablePaneAdapter 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter class
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 05d34e3ec84db48e50328b99c38abf1ef73747b4
ms.lasthandoff: 02/24/2017

---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter 클래스
`CWnd`파생 창에 대해 도킹 지원을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|래핑된 창을 반환합니다.|  
|[CDockablePaneAdapter::LoadState](#loadstate)|(재정의 [CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CDockablePaneAdapter::SaveState](#savestate)|(재정의 [CDockablePane::SaveState](http://msdn.microsoft.com/en-us/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>주의  
 사용 하는 경우 프레임 워크가이 클래스의 개체를 인스턴스화하는 일반적으로 [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 또는 [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) 메서드.  
  
 사용자 지정 하려는 경우는 `CDockablePaneAdapter` 동작에서 새 클래스를 파생 하 고 사용 하 여 탭된 창에는 런타임 클래스 정보를 설정 했습니다 [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDockablePaneAdapter.h  
  
##  <a name="getwrappedwnd"></a>CDockablePaneAdapter::GetWrappedWnd  
 도킹 가능한 창 어댑터에 대 한 기본 창을 반환합니다.  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 래핑된 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 래핑된 창에 액세스 하려면이 함수를 사용 합니다.  
  
##  <a name="loadstate"></a>CDockablePaneAdapter::LoadState  
 레지스트리에서 창 상태를 로드합니다.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `nIndex`  
 프로필 인덱스입니다.  
  
 [in] `uiID`  
 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="savestate"></a>CDockablePaneAdapter::SaveState  
 레지스트리에 있는 창의 상태를 저장합니다.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 프로필 이름입니다.  
  
 [in] `nIndex`  
 프로필 인덱스 (기본값: 창 컨트롤 ID)입니다.  
  
 [in] `uiID`  
 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="setwrappedwnd"></a>CDockablePaneAdapter::SetWrappedWnd  
 도킹 가능한 창 어댑터에 대 한 기본 창을 설정합니다.  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 래핑할 창 어댑터에 대 한 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)

