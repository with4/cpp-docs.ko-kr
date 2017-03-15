---
title: "CListView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListView
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- CListView class
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
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
ms.openlocfilehash: ebf6c93aa6d88d1942af4ecb9e3373fa57d84b65
ms.lasthandoff: 02/24/2017

---
# <a name="clistview-class"></a>CListView 클래스
및 목록 컨트롤의 사용을 간소화 [CListCtrl](../../mfc/reference/clistctrl-class.md), MFC의 문서 뷰 아키텍처를 목록 컨트롤 기능을 캡슐화 하는 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|`CListView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|뷰와 연결 된 목록 컨트롤을 반환 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|지정 된 이미지 목록의 목록 보기에서 제거합니다.|  
  
## <a name="remarks"></a>주의  
 이 아키텍처에 대 한 자세한 내용은 참조에 대 한 개요는 [CView](../../mfc/reference/cview-class.md) 클래스와 있습니다 명시 된 상호 참조 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcview.h  
  
##  <a name="a-nameclistviewa--clistviewclistview"></a><a name="clistview"></a>CListView::CListView  
 `CListView` 개체를 생성합니다.  
  
```  
CListView();
```  
  
##  <a name="a-namegetlistctrla--clistviewgetlistctrl"></a><a name="getlistctrl"></a>CListView::GetListCtrl  
 뷰와 연결 된 목록 컨트롤에 대 한 참조를 가져오려면이 함수를 호출 합니다.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 뷰와 연결 된 목록 컨트롤에 대 한 참조입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCListView #&7;](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="a-nameremoveimagelista--clistviewremoveimagelist"></a><a name="removeimagelist"></a>CListView::RemoveImageList  
 지정 된 이미지 목록의 목록 보기에서 제거합니다.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 `nImageList`  
 제거할 이미지의&0;부터 시작 하는 인덱스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 ROWLIST](../../visual-cpp-samples.md)   
 [CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)

