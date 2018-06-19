---
title: 도구 설명에 대 한 TTN_NEEDTEXT 알림 처리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TTN_NEEDTEXT
dev_langs:
- C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce7a4d6dc6edf122b5d9b5301768dea8389e771e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345919"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>도구 설명에 대한 TTN_NEEDTEXT 알림 처리
일부로 [도구 설명을 사용 하도록 설정](../mfc/enabling-tool-tips.md)를 처리 하는 **TTN_NEEDTEXT** 소유자 창의 메시지 맵에 다음 항목을 추가 하 여 메시지:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 이 단추 텍스트가 필요할 때 호출 되는 멤버 함수입니다.  
  
 도구 설명의 ID는 항상 0입니다.  
  
 클래스 정의에 처리기 함수를 다음과 같이 선언 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 기울임꼴로 표시 된 매개 변수는:  
  
 `id`  
 알림을 전송 하는 컨트롤의 식별자입니다. 사용되지 않습니다. 컨트롤 id에서 가져온 것은 **NMHDR** 구조입니다.  
  
 `pNMHDR`  
 에 대 한 포인터는 [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) 구조입니다. 이 구조에 대해서도 설명에서 추가로 [TOOLTIPTEXT 구조](../mfc/tooltiptext-structure.md)합니다.  
  
 `pResult`  
 결과 코드에 대 한 포인터를 반환 하기 전에 설정할 수 있습니다. **TTN_NEEDTEXT** 처리기를 무시할 수는 `pResult` 매개 변수입니다.  
  
 폼 보기 알림 처리기의 예:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 호출 `EnableToolTips` (이 조각에서 가져온 `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

