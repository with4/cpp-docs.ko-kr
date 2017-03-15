---
title: "CMFCPropertyGridToolTipCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridToolTipCtrl::PreTranslateMessage
- ~CMFCPropertyGridToolTipCtrl
- PreTranslateMessage
- CMFCPropertyGridToolTipCtrl.~CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl.PreTranslateMessage
- CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl class
- CMFCPropertyGridToolTipCtrl class, destructor
- PreTranslateMessage method
- ~CMFCPropertyGridToolTipCtrl destructor
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
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
ms.openlocfilehash: e5290706799dcd253205ac74dad72cd7783d19dd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl 클래스
도구 설명에는 구현 하는 컨트롤의 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md) 사용 하 여 도구 설명을 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCPropertyGridToolTipCtrl::Create](#create)|도구 설명 컨트롤에 대 한 창을 만듭니다.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|비활성화 하 고 도구 설명 컨트롤을 숨깁니다.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Tooltip 컨트롤의 마지막 위치 좌표를 반환합니다.|  
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|도구 설명 컨트롤을 숨깁니다.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|클래스에서 사용 하는 [CWinApp](../../mfc/reference/cwinapp-class.md) 으로 디스패치 되기 전에 창 메시지를 변환 하는 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. (재정의 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|도구 설명 텍스트와 도구 설명 창의 가장자리 사이의 간격을 설정합니다.|  
|[CMFCPropertyGridToolTipCtrl::Track](#track)|도구 설명 컨트롤에 표시 됩니다.|  
  
## <a name="remarks"></a>주의  
 속성 이름에는 포인터를 놓으면 도구 설명이 표시 됩니다. [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) 사용자가 쉽게 읽을 수 있도록 클래스는 도구 설명이 표시 됩니다. 일반적으로 도구 설명의 위치는 포인터의 위치에 따라 결정 됩니다. 이 클래스를 사용 하 여 도구 설명 속성 이름 위에 나타나고 속성 이름을 완벽 하 게 볼 수 있도록 자연 속성 확장와 비슷합니다.  
  
 MFC 자동으로이 컨트롤을 만들고에서 사용 하 여 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)합니다.  
  
## <a name="example"></a>예제  
 개체를 생성 하는 방법은 다음 예제는 `CMFCPropertyGridToolTipCtrl` 클래스 및 도구 설명 컨트롤을 표시 하는 방법입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp&23;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxpropertygridtooltipctrl.h  
  
##  <a name="a-namecmfcpropertygridtooltipctrla--cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a>CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl  
 `CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.  
  
```  
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```  
  
##  <a name="a-namecreatea--cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a>CMFCPropertyGridToolTipCtrl::Create  
 도구 설명 컨트롤에 대 한 창을 만듭니다.  
  
```  
BOOL Create(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndParent`  
 부모 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 창 성공적으로 만들었습니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="a-namedeactivatea--cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a>CMFCPropertyGridToolTipCtrl::Deactivate  
 비활성화 하 고 도구 설명 컨트롤을 숨깁니다.  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 설정 마지막 위치와 텍스트를 빈 값, 미래에 대 한 호출이 있도록 [CMFCPropertyGridToolTipCtrl::Track](#track) 도구 설명을 표시 합니다.  
  
##  <a name="a-namegetlastrecta--cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a>CMFCPropertyGridToolTipCtrl::GetLastRect  
 Tooltip 컨트롤의 마지막 위치 좌표를 반환합니다.  
  
```  
void GetLastRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `rect`  
 Tooltip 컨트롤의 마지막 위치를 포함합니다.  
  
##  <a name="a-namehidea--cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a>CMFCPropertyGridToolTipCtrl::Hide  
 도구 설명 컨트롤을 숨깁니다.  
  
```  
void Hide();
```  
  
##  <a name="a-namesettextmargina--cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a>CMFCPropertyGridToolTipCtrl::SetTextMargin  
 도구 설명 텍스트와 도구 설명 창의 가장자리 사이의 간격을 설정합니다.  
  
```  
void SetTextMargin(int nTextMargin);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nTextMargin`  
 컨트롤 도구 설명 텍스트와 도구 설명 창의 가장자리 사이의 간격을 지정합니다. 기본값은 10 픽셀입니다.  
  
##  <a name="a-nametracka--cmfcpropertygridtooltipctrltrack"></a><a name="track"></a>CMFCPropertyGridToolTipCtrl::Track  
 도구 설명 컨트롤에 표시 됩니다.  
  
```  
void Track(
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 도구 설명 컨트롤의 크기와 위치를 지정합니다.  
  
 [in] `strText`  
 도구 설명에 표시할 텍스트를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정 된 크기와 위치에 도구 설명 컨트롤 표시 `rect`합니다. 위치, 크기 및 텍스트 마지막으로이 메서드가 호출 된 이후 변경 되지 않은 경우이 메서드는 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

