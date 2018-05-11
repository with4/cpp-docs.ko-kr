---
title: CTreeView 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d19d4958de2f7909f2072b2ae2f59c00e63d65a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ctreeview-class"></a>CTreeView 클래스
및 트리 컨트롤의 사용을 간소화 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), MFC의 문서 뷰 아키텍처와의 트리 컨트롤 기능을 캡슐화 하는 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|`CTreeView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|뷰와 연결 된 트리 컨트롤을 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 이 아키텍처에 대 한 자세한 내용은 참조에 대 한 개요는 [CView](../../mfc/reference/cview-class.md) 클래스와 있습니다 언급 된 상호 참조 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcview.h  
  
##  <a name="ctreeview"></a>  CTreeView::CTreeView  
 `CTreeView` 개체를 생성합니다.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl  
 뷰와 연결 된 트리 컨트롤에 대 한 참조를 반환 합니다.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>참고 항목  
 [CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl 클래스](../../mfc/reference/ctreectrl-class.md)
