---
title: "헤더 컨트롤 알림 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a442e6aadf7c91918cd523c29330e79c753b115c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-header-control-notifications"></a>헤더 컨트롤 알림 처리
뷰 또는 대화 상자 클래스를 사용 하 여 속성 창을 만들는 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) 모든 헤더 컨트롤에 대해 switch 문 사용 하는 처리기 함수 ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) 알림 메시지를 처리 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)). 사용자가 클릭 하거나 헤더 항목을 끌 항목과 등 사이의 구분선을 두 번 클릭할 때 부모 창에 알림이 전송 됩니다.  
  
 헤더 컨트롤에 연결 된 알림 메시지에 나열 된 [헤더 컨트롤 참조](http://msdn.microsoft.com/library/windows/desktop/bb775239) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

