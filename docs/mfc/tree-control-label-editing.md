---
title: "트리 컨트롤 레이블 편집 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c46616914f9cf6d1069702c16cdd03f272d6561c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-label-editing"></a>트리 컨트롤 레이블 편집
사용자는 트리 컨트롤에 항목의 레이블을 직접 편집할 수 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 올려진는 **TVS_EDITLABELS** 스타일입니다. 사용자 포커스가 있는 항목의 레이블을 클릭 하 여 편집을 시작 합니다. 응용 프로그램을 사용 하 여 편집 시작는 [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) 멤버 함수입니다. 트리 컨트롤 알림 편집할 때 시작 되 고 취소 하거나 완료 때 보냅니다. 편집이 완료 되 면 책임이 있습니다 항목의 레이블을 업데이트 해당 되는 경우입니다.  
  
 레이블 편집을 시작할 때, 트리 컨트롤에서 보냅니다는 [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) 알림 메시지입니다. 이 알림 메시지를 처리 하 여 일부 레이블을 편집할 수 수 있으며 다른 사람이 편집을 방지할 수 있습니다. 편집을 사용 하면 0을 반환 하며, 되지 0이 아닌 값을 반환 합니다.  
  
 레이블 편집 취소 되거나 완료 될, 트리 컨트롤 보냅니다는 [TVN_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515) 알림 메시지입니다. `lParam` 매개 변수는의 주소는 [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) 구조입니다. **항목** 멤버는 한 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 항목을 식별 하 고 편집 된 텍스트를 포함 하는 구조입니다. 항목의 레이블을 업데이트, 필요한 경우 아마도 편집된 된 문자열을 확인 한 후 책임이 있습니다. **pszText** 소속 `TV_ITEM` 편집이 취소 하는 경우 0입니다.  
  
 레이블 편집, 일반적으로 응답 하는 동안는 [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) 알림 메시지를 사용 하 여 레이블 편집에 사용 되는 편집 컨트롤에 대 한 포인터를 가져올 수 있습니다는 [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) 멤버 함수입니다. 편집 컨트롤을 호출할 수 있습니다 [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) 멤버 함수를 입력할 수 있는 텍스트 또는 하위 클래스를 가로채 고 잘못 된 문자가 삭제 편집 컨트롤의 크기를 제한 합니다. 단, 편집 컨트롤이 표시 되도록 *후* **TVN_BEGINLABELEDIT** 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

