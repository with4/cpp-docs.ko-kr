---
title: Rich Edit 컨트롤의 단락 서식 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 113d47a88f0de7ddd12f474678705688569ad50d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Rich Edit 컨트롤의 단락 서식 지정
Rich edit 컨트롤의 멤버 함수를 사용할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 단락 서식을 지정 하 고 서식 지정 정보를 검색 합니다. 단락 형식 지정 특성에는 맞춤, 탭, 들여쓰기 및 번호 매김이 포함됩니다.  
  
 단락을 사용 하 여 서식을 적용할 수는 [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) 멤버 함수입니다. 현재 선택한 텍스트에 대 한 서식을 단락을 확인 하려면는 [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) 멤버 함수입니다. [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) 구조는 단락 특성을 지정 하려면 이러한 멤버 함수와 함께 사용 합니다. 중요 한 멤버 중 하나 **PARAFORMAT** 은 **dwMask**합니다. `SetParaFormat`, **dwMask** 이 함수 호출으로 설정할 단락 특성을 지정 합니다. `GetParaFormat` 첫 번째 단락에;의 특성을 보고 **dwMask** 선택 영역 전체에 걸쳐 일관적인 특성을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

