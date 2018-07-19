---
title: 도구 설명을 사용 하도록 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 598583360eca2a65a5352fc9d284d8d359ac021c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346138"
---
# <a name="enabling-tool-tips"></a>도구 설명을 사용하도록 설정
창의 자식 컨트롤에 대한 도구 설명 지원을 설정할 수 있습니다(예: 폼 뷰 또는 대화 상자의 컨트롤).  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>창의 자식 컨트롤에 대해 도구 설명을 사용하도록 설정하려면  
  
1.  도구 설명을 제공하려는 창에 대해 `EnableToolTips`를 호출합니다.  
  
2.  각 컨트롤에 대 한 문자열을 제공 하면 [TTN_NEEDTEXT 알림](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) 처리기입니다. 처리기는 자식 컨트롤을 포함하는 창의 메시지 맵에 있습니다(예: 폼 뷰 클래스). 이 처리기를 호출 해야 하는 함수는 컨트롤을 식별 하 고 설정 **pszText** 도구 설명 컨트롤에서 사용 하는 텍스트를 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

