---
title: "애니메이션 컨트롤이 보내는 알림 | Microsoft Docs"
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
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c57a33bf4b13397d4f296ef4e5aa8e137c2d3594
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-sent-by-animation-controls"></a>애니메이션 컨트롤이 보내는 알림
애니메이션 컨트롤 ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 두 가지 유형의 알림 메시지를 보냅니다. 가 발송의 형태로 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지입니다.  
  
 [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) 애니메이션 컨트롤 클립 재생 시작 될 때 전송 됩니다. [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) 애니메이션 컨트롤 완료 했거나 클립 재생이 중지 되었을 때 메시지가 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAnimateCtrl 사용](../mfc/using-canimatectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

