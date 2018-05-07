---
title: 창 개체 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c00649c51e34bbbac7adbf7aa5f3c7d04790ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-window-objects"></a>창 개체 작업
두 종류의 작업에 대 한 windows 호출 작업:  
  
-   Windows 메시지 처리  
  
-   창에 그리기  
  
 자신의 자식 창을 포함 하 여 모든 창에서 Windows 메시지를 처리 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 메시지 c + + 창 클래스에 매핑됩니다. 다음 클래스에 메시지 처리기 멤버 함수를 작성 합니다.  
  
 보기에서 발생 하는 프레임 워크 응용 프로그램에서 대부분의 그리기 인 [OnDraw](../mfc/reference/cview-class.md#ondraw) 멤버 함수는 창 내용 그려야 할 때마다 호출 됩니다. 사용자가 창을 보기의 자식이 면 있습니다에 위임할 수 뷰의 그리기 중 일부를 자식 창 함으로써 `OnDraw` 창의 멤버 함수 중 하나를 호출 합니다.  
  
 어떤 경우 든, 그리기에 대 한 장치 컨텍스트를 해야 합니다. 스톡 펜, 브러시 및 창과 연결 된 장치 컨텍스트에 포함 된 기타 그래픽 개체를 사용할 수 있습니다. 또는 필요한 그리기 효과 가져올이 개체를 수정할 수 있습니다. 디바이스 컨텍스트를 원하는 대로 설정, 멤버 함수를 호출 클래스의 [CDC](../mfc/reference/cdc-class.md) (디바이스 컨텍스트 클래스) 줄, 도형 및 텍스트를 그리는 데; 색상을 사용 하도록 및 좌표계에서 실행 되도록 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)  
  
-   [뷰에 그리기](../mfc/drawing-in-a-view.md)  
  
-   [장치 컨텍스트](../mfc/device-contexts.md)  
  
-   [그래픽 개체](../mfc/graphic-objects.md)  
  
## <a name="see-also"></a>참고 항목  
 [창 개체](../mfc/window-objects.md)

