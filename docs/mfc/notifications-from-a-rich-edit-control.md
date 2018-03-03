---
title: "Edit 컨트롤 Rich에서 보내는 알림 | Microsoft Docs"
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
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>Rich Edit 컨트롤에서 보내는 알림
알림 메시지 보고서 컨트롤을 편집 하는 다양 한 기능의 영향을 주는 이벤트 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). 이러한 부모 창에서 처리할 수 또는 메시지 리플렉션을 사용 하는 rich edit 컨트롤 자체. Rich edit 컨트롤 모든 편집 컨트롤 뿐 아니라 몇 가지 추가 구성을 사용 하는 알림 메시지를 지원 합니다. 알림 메시지를 rich edit 컨트롤의 부모 창 "이벤트 마스크입니다."를 설정 하 여 보내는 것을 확인할 수 있습니다.  
  
 Rich edit 컨트롤에 대 한 이벤트 마스크를 설정 하려면는 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) 멤버 함수입니다. 사용 하 여 rich edit 컨트롤에 대 한 현재 이벤트 마스크를 검색할 수 있습니다는 [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) 멤버 함수입니다.  
  
 다음 단락에서는 여러 특정 알림 메시지 및 해당 용도 나열합니다.  
  
-   **EN_MSGFILTER** 처리는 **EN_MSGFILTER** 중 하나는 풍부한 컨트롤 또는 해당 부모 창 편집, 필터링 모든 키보드 및 마우스를 컨트롤에 대 한 입력, 알림 클래스 할당할 수 있습니다. 처리기 키보드 또는 마우스 메시지가 처리 되지 않도록 방지할 수 또는 지정 된 수정 하 여 메시지를 변경할 수 [메시지 필터](http://msdn.microsoft.com/library/windows/desktop/bb787936) 구조입니다.  
  
-   **EN_PROTECTED** 처리는 **EN_PROTECTED** 알림 메시지를 사용자가 보호 된 텍스트를 수정 하려고 하는 시기를 검색 합니다. 텍스트 범위를 protected로 표시 하려면 보호 된 문자 효과 설정할 수 있습니다. 자세한 내용은 참조 [Rich Edit 컨트롤에서 문자 서식](../mfc/character-formatting-in-rich-edit-controls.md)합니다.  
  
-   **EN_DROPFILES** 처리 하 여 서식 있는 편집 컨트롤에 있는 파일을 삭제 하려면 사용자를 사용 하도록 설정할 수는 **EN_DROPFILES** 알림 메시지입니다. 지정 된 [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) 구조 삭제 되는 파일에 대 한 정보를 포함 합니다.  
  
-   **EN_SELCHANGE** 응용 프로그램을 처리 하 여 현재 선택이 변경 될 때를 감지할 수는 **EN_SELCHANGE** 알림 메시지입니다. 알림 메시지를 지정 된 [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) 새 선택에 대 한 정보가 포함 된 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

