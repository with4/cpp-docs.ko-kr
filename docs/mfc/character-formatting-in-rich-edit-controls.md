---
title: "Rich Edit 컨트롤의 문자 서식 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 86b9686396d8f3bd6abd67f5a1f33be0d20bdc16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="character-formatting-in-rich-edit-controls"></a>Rich Edit 컨트롤의 문자 서식 지정
Rich edit 컨트롤의 멤버 함수를 사용할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 문자 서식을 지정 하 고 서식 지정 정보를 검색 합니다. 문자에 대 한 서체, 크기, 색 및 효과 굵게, 기울임꼴 등을 지정할 수 있으며 보호.  
  
 문자를 사용 하 여 서식을 적용할 수 있습니다는 [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) 및 [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) 멤버 함수입니다. 선택한 텍스트에 대 한 서식을 현재 문자를 확인 하려면 사용 하 여는 [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) 멤버 함수입니다. [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) 구조는 문자 특성을 지정 하려면 이러한 멤버 함수와 함께 사용 합니다. 중요 한 멤버 중 하나 **CHARFORMAT** 은 **dwMask**합니다. `SetSelectionCharFormat` 및 `SetWordCharFormat`, **dwMask** 지정 된 문자 특성을이 함수 호출으로 설정 됩니다. `GetSelectionCharFormat`선택 영역의; 첫 번째 문자의 특성을 보고 **dwMask** 선택 영역 전체에 걸쳐 일관적인 특성을 지정 합니다.  
  
 또한 get 하 고 설정할 수는 "기본 문자 형식" 이후에 삽입 된 문자에 적용 되는 합니다. 예를 들어 응용 프로그램의 기본 문자를 굵게 서식 설정 하는 경우 사용자는 문자를 입력 한 다음 문자를 굵게 표시 됩니다. 사용 하 여 가져오고 기본 문자 형식을 지정 하는 [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) 및 [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) 멤버 함수입니다.  
  
 "보호" 문자 특성이 텍스트의 모양을 변경 되지 않습니다. Rich edit 컨트롤의 부모 창 보냅니다 사용자가 보호 된 텍스트를 수정 하려고 하는 경우는 **EN_PROTECTED** 알림 메시지를 허용 하거나 비어 있지 부모 창입니다. 이 알림 메시지를 받으려면 활성화 해야를 사용 하 여는 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) 멤버 함수입니다. 이벤트 마스크에 대 한 자세한 내용은 참조 [서식 있는 편집 컨트롤에서 알림](../mfc/notifications-from-a-rich-edit-control.md)이 항목의 뒷부분에 나오는 합니다.  
  
 전경색 문자 특성은 있지만 배경색 rich edit 컨트롤의 속성입니다. 명령 프롬프트 창의 배경색을 설정 하려면는 [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

