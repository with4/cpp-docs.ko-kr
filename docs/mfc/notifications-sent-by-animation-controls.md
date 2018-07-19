---
title: 애니메이션 컨트롤이 보내는 알림 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1696389ce3dc40c5d02ec660ebaeb6bf3e6c3ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345251"
---
# <a name="notifications-sent-by-animation-controls"></a>애니메이션 컨트롤이 보내는 알림
애니메이션 컨트롤 ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 두 가지 유형의 알림 메시지를 보냅니다. 가 발송의 형태로 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다.  
  
 [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) 애니메이션 컨트롤 클립 재생 시작 될 때 전송 됩니다. [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) 애니메이션 컨트롤 완료 했거나 클립 재생이 중지 되었을 때 메시지가 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAnimateCtrl 사용](../mfc/using-canimatectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

