---
title: 목록 컨트롤에서 알림 메시지 처리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5412bbf1fcb7e139394b9563965244080e5c179
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932083"
---
# <a name="processing-notification-messages-in-list-controls"></a>목록 컨트롤에서 알림 메시지 처리
사용자가 열 머리글을 클릭 아이콘, 레이블 및 이런 식으로 목록 컨트롤을 편집 ([CListCtrl](../mfc/reference/clistctrl-class.md))를 해당 부모 창 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 열 머리글을 클릭할 때 클릭 한 열에서와 같이 Microsoft Outlook의 내용에 따라 항목을 정렬 하는 것이 좋습니다.  
  
 뷰 또는 대화 상자 클래스에 있는 목록 컨트롤에서 WM_NOTIFY 메시지를 처리 합니다. 속성 창을 사용 하 여 만들기는 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch 문 사용 하는 처리기 함수는 알림 메시지 처리 되 고 기반 합니다.  
  
 목록 컨트롤의 부모 창에 보낼 수 알림 목록에 대 한 참조 [목록 보기 컨트롤 참조](http://msdn.microsoft.com/library/windows/desktop/bb774737) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

