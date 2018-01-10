---
title: "방법: 사용자 인터페이스 개체 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91e6d13e840c29d3ea9600183fafd9260966a2f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-update-user-interface-objects"></a>방법: 사용자 인터페이스 개체 업데이트
일반적으로, 메뉴와 도구 모음 단추는 하나 이상의 상태를 포함 합니다. 예를 들어 현재 컨텍스트에서 사용할 수 없는 경우 메뉴 항목을 흐리게 흐리게 표시 됩니다. 메뉴 항목 checked 또는 unchecked 될 수도 있습니다. 도구 모음 단추를 사용할 수 없는 경우에 비활성화 수 또는 확인할 수 있습니다.  
  
 메뉴 항목에서 처리 하는 명령을 생성 하는 경우 상태가 변경 됨을 논리적으로 프로그램으로 이러한 항목, 의견을 언급 해서도, 문서 상태를 업데이트 하는 것이 좋습니다 문서가 메뉴 항목을 업데이트 합니다. 문서는 것이 업데이트의 기반이 되는 정보를 포함 합니다.  
  
 명령에 여러 사용자 인터페이스 개체 (메뉴 항목 및 도구 모음 단추), 동일한 처리기 함수에 라우팅됩니다. 한 곳에서 해당 하는 사용자 인터페이스 개체에 대 한 사용자 인터페이스 업데이트 코드를 캡슐화합니다.  
  
 프레임 워크 사용자 인터페이스 개체를 자동으로 업데이트 하기 위한 편리한 인터페이스를 제공 합니다. 다른 방법으로 업데이트를 수행 하도록 선택할 수 있습니다 하지만 제공 하는 인터페이스는 효율적이 고 사용 하기 쉽습니다.  
  
 업데이트 처리기 사용을 설명 하는 다음 항목:  
  
-   [업데이트 처리기가 호출](../mfc/when-update-handlers-are-called.md)  
  
-   [ON_UPDATE_COMMAND_UI 매크로](../mfc/on-update-command-ui-macro.md)  
  
-   [CCmdUI 클래스](../mfc/the-ccmdui-class.md)  
  
## <a name="see-also"></a>참고 항목  
 [메뉴](../mfc/menus-mfc.md)

