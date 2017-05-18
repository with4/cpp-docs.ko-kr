---
title: "CTreeView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeView class, common controls
- CTreeView class
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c317d91a07b5cb45b58ec4c4af2e9ee0f3b24e28
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ctreeview-class"></a>CTreeView 클래스
및 트리 컨트롤의 사용을 간소화 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), MFC의 문서 뷰 아키텍처를 트리 컨트롤 기능을 캡슐화 하는 클래스입니다.  
  
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
  
## <a name="remarks"></a>주의  
 이 아키텍처에 대 한 자세한 내용은 참조에 대 한 개요는 [CView](../../mfc/reference/cview-class.md) 클래스와 있습니다 명시 된 상호 참조 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcview.h  
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 `CTreeView` 개체를 생성합니다.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
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

