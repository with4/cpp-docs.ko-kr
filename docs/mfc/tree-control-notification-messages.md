---
title: "트리 컨트롤 알림 메시지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 60552547087ce97a92429c94654238f9c7d2870c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-notification-messages"></a>트리 컨트롤 알림 메시지
트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))으로 다음 알림 메시지를 전송 **WM_NOTIFY** 메시지:  
  
|알림 메시지|설명|  
|--------------------------|-----------------|  
|**TVN_BEGINDRAG**|끌어서 놓기 작업의 시작을 알림|  
|**TVN_BEGINLABELEDIT**|내부에서 레이블 편집의 시작을 알림|  
|**TVN_BEGINRDRAG**|마우스 오른쪽 단추를 사용 하는 끌어서 놓기 작업의 시작을 알림|  
|**TVN_DELETEITEM**|특정 항목의 삭제를 알림|  
|**TVN_ENDLABELEDIT**|레이블 편집 끝났음을 신호로 보냅니다.|  
|**TVN_GETDISPINFO**|트리 컨트롤 항목을 표시 해야 하는 요청 정보|  
|**TVN_ITEMEXPANDED**|하위 항목의 부모 항목의 목록을 확장 또는 축소 되었음을 신호|  
|**TVN_ITEMEXPANDING**|하위 항목의 부모 항목의 목록을 확장 하거나 축소할 수 하려고 하는 신호|  
|**TVN_KEYDOWN**|키보드 이벤트를 알림|  
|**TVN_SELCHANGED**|한 항목에서 다른 선택 영역이 변경 신호|  
|**TVN_SELCHANGING**|선택 영역에는 한 항목에서 변경할 수 하려고 하는 신호|  
|**TVN_SETDISPINFO**|항목에 대 한 유지 관리 정보를 업데이트 하려면 알림|  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

