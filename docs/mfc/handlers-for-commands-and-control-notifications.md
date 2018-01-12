---
title: "명령 및 컨트롤 알림에 대 한 처리기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 748bdd1a2ce6b94a2c935df94de68767ee36875e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-commands-and-control-notifications"></a>명령 및 컨트롤 알림에 대한 처리기
명령 또는 컨트롤 알림 메시지에 대 한 기본 처리기가 없는 있습니다. 따라서 이러한 메시지의이 범주에 대 한 처리기를 명명 규칙만 바인딩됩니다. 명령 또는 컨트롤 알림 처리기에 매핑할 때는 속성 창에 명령 ID 또는 알림 컨트롤 코드에 따라 이름을 제안 합니다. 제안된 된 이름을 적용,를 변경 하거나 바꿀 수 있습니다.  
  
 규칙 나타내는 사용자 인터페이스 개체에 대 한 두 범주에에서 대 한 처리기를 이름을 제안 합니다. 따라서 편집 메뉴에서 잘라내기 명령에 대 한 처리기 이름은 수 있습니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 잘라내기 명령을 일반적으로 구현 되므로 응용 프로그램에서 때문에 프레임 워크를 명령 ID로 잘라내기 명령에 대 한 미리 정의 **ID_EDIT_CUT**합니다. 모든 미리 정의 된 명령 Id의 목록을 보려면 AFXRES 파일을 참조 합니다. 8. 자세한 내용은 참조 [표준 명령](../mfc/standard-commands.md)합니다.  
  
 규칙에 대 한 처리기를 제안 하는 또한는 **BN_CLICKED** "My Button" 레이블이 붙은 단추에서 알림 메시지 이름이 지정 됩니다  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 이 명령은 ID가 할당할 수 있습니다 `IDC_MY_BUTTON` 이므로 응용 프로그램 관련 사용자 인터페이스 개체에 해당 합니다.  
  
 메시지의 두 범주 인수를 가져오지 않고 및 아무 값도 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
