---
title: "CMFCImageEditorPaletteBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorPaletteBar class
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
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
ms.openlocfilehash: f6b987a27b43d713835a71dd5c31587020f23f2f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar 클래스
이미지 편집기 대화 상자 팔레트 모음 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|도구 모음 단추의 높이 반환합니다. (재정의 [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|도구 모음 테두리 확장 단추를 표시할 수 있는지 여부를 결정 합니다. (재정의 [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
  
### <a name="remarks"></a>주의  
 이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.  
  
 이미지 편집기 대화 상자에서 팔레트 표시줄을 표시 하려면이 클래스를 사용 하는 프레임 워크입니다. 이미지 편집기 대화 상자에 대 한 자세한 내용은 참조 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afximageeditordialog.h  
  
##  <a name="getrowheight"></a>CMFCImageEditorPaletteBar::GetRowHeight  
 도구 모음 단추의 높이 반환합니다.  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음에서 각 단추의 높이입니다.  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable  
 도구 모음 테두리 확장 단추를 표시할 수 있는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 `FALSE`을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)

