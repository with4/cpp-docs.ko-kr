---
title: COleResizeBar 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3046fa4c9446afeba45fd41a6b571ccf58f2cfb
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040118"
---
# <a name="coleresizebar-class"></a>COleResizeBar 클래스
내부 OLE 항목의 크기 변경을 지원하는 컨트롤 막대의 한 종류입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|`COleResizeBar` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|및 Windows 자식 창을 초기화 만들어지고 연결 하는 `COleResizeBar` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `COleResizeBar` 로 표시 된 개체는 [CRectTracker](../../mfc/reference/crecttracker-class.md) 빗금된 테두리가 있는 및 외부 크기 조정 핸들입니다.  
  
 `COleResizeBar` 개체는 프레임 창 개체에서 파생 된 일반적으로 포함 된 멤버는 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) 클래스입니다.  
  
 자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar  
 `COleResizeBar` 개체를 생성합니다.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>설명  
 호출 **만들기** 크기 조정 막대 개체를 만듭니다.  
  
##  <a name="create"></a>  COleResizeBar::Create  
 자식 창을 만들고 변수와 연결 된 `COleResizeBar` 개체입니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentWnd*  
 크기 조정 막대의 부모 창에 대 한 포인터입니다.  
  
 *dwStyle*  
 지정 된 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 특성입니다.  
  
 *nID*  
 크기 조정 막대의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 크기 조정 막대 만들어진 경우 0이 아닌 그렇지 않으면 0입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleServerDoc 클래스](../../mfc/reference/coleserverdoc-class.md)
