---
title: "CMFCDragFrameImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDragFrameImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCDragFrameImpl class
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
caps.latest.revision: 26
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
ms.openlocfilehash: 8c21e3bcca36838e40cb7a0edcddba432ecb0540
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl 클래스
`CMFCDragFrameImpl` 클래스는 사용자가 표준 도킹 모드에서 창을 끌 때 나타나는 끌기 사각형을 그립니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCDragFrameImpl  
```  
  
## <a name="remarks"></a>주의  
 이 클래스의 개체가 각각에 포함 된 [CPane 클래스](../../mfc/reference/cpane-class.md) 개체입니다. 사용 하는 각 창에 따라서는 `CanFloat` 메서드는 사용자가 끌어올 때 끌기 사각형을 표시 합니다.  
  
 사용 하 여 끌기 사각형의 두께 제어할 수 [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat]--brokenlink--(afx-global-data-structure.md#m_ndragframethicknessfloat) 및 [afx_global_data:: m_ndragframethicknessdock](afx-global-data-structure.md#m_ndragframethicknessdock)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdragframeimpl.h  
  
##  <a name="enddrawdragframe"></a>CMFCDragFrameImpl::EndDrawDragFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bClearInternalRects`  
  
### <a name="remarks"></a>주의  
  
##  <a name="init"></a>CMFCDragFrameImpl::Init  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Init(CWnd* pDraggedWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDraggedWnd`  
  
### <a name="remarks"></a>주의  
  
##  <a name="movedragframe"></a>CMFCDragFrameImpl::MoveDragFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void MoveDragFrame(BOOL bForceMove = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bForceMove`  
  
### <a name="remarks"></a>주의  
  
##  <a name="placetabpredocking"></a>CMFCDragFrameImpl::PlaceTabPreDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,  
    BOOL bFirstTime);  
  
void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pTabbedBar`  
 [in] `bFirstTime`  
 [in] `pCBarToPlaceOn`  
  
### <a name="remarks"></a>주의  
  
##  <a name="removetabpredocking"></a>CMFCDragFrameImpl::RemoveTabPreDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOldTargetBar`  
  
### <a name="remarks"></a>주의  
  
##  <a name="resetstate"></a>CMFCDragFrameImpl::ResetState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ResetState();
```  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane 클래스](../../mfc/reference/cpane-class.md)
