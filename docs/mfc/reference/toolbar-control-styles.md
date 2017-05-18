---
title: "ToolBar 컨트롤 스타일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1c50009a50c5b80e007add9de679315df6aecea9
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="toolbar-control-styles"></a>ToolBar 컨트롤 스타일
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 단추의 동작 및 모양을 결정 하는 스타일 플래그 집합이 했습니다. 호출 하 여 이러한 플래그의 조합을 설정할 수 있습니다 [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)합니다. 이 항목에는 스타일 플래그 값 및 해당 의미가 나열됩니다.  
  
## <a name="property-values"></a>속성 값  
 다음 값에 따라 컨트롤에서 제공되는 단추 형식이 결정됩니다.  
  
 TBBS_BUTTON  
 표준 누름 단추입니다(기본값).  
  
 TBBS_CHECKBOX  
 확인란입니다.  
  
 TBBS_CHECKGROUP  
 확인란 그룹의 시작 부분입니다.  
  
 TBBS_GROUP  
 여러 단추 그룹의 시작 부분입니다.  
  
 TBBS_SEPARATOR  
 구분선입니다.  
  
 다음 값은 컨트롤의 현재 상태를 나타냅니다.  
  
 TBBS_CHECKED  
 확인란이 선택되었습니다.  
  
 TBBS_DISABLED  
 컨트롤이 비활성화되었습니다.  
  
 TBBS_INDETERMINATE  
 확인란이 결정되지 않은 상태입니다.  
  
 TBBS_PRESSED  
 단추를 눌렀습니다.  
  
 다음 값은 도구 모음에 있는 단추의 레이아웃을 변경합니다.  
  
 TBBS_BREAK  
 새 줄에 항목을 배치하거나 열을 구분하지 않기 새 열에 배치합니다.  
  
## <a name="remarks"></a>주의  
 현재 스타일에 저장 된 [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)합니다. 새 값을 설정 하지 않은 `m_nStyle` 를 직접 일부 파생 된 클래스를 호출할 때 추가 처리를 수행 하기 때문에 `SetStyles`합니다.  
  
 시각화 관리자는 각 상태에서 단추의 모양을 결정합니다. 참조 [시각화 관리자](../../mfc/visualization-manager.md) 에 대 한 자세한 내용은 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [시각화 관리자](../../mfc/visualization-manager.md)



