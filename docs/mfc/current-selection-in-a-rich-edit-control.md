---
title: Rich Edit 컨트롤의 현재 선택 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 782984bc53bc16f8dc89e4e705811fef24b8931e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="current-selection-in-a-rich-edit-control"></a>Rich Edit 컨트롤의 현재 선택
사용자 서식 있는 편집 컨트롤에서 텍스트를 선택할 수 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 마우스나 키보드를 사용 하 여 합니다. 현재 선택 영역이 선택 된 문자의 범위 또는 문자가 없는 경우 삽입 지점의 위치를 선택 합니다. 응용 프로그램 현재 선택 영역에 대 한 정보를 가져올 수, 현재 선택 영역을 설정, 현재 선택 영역이 변경 하 고 표시 또는 숨기기 선택 항목 강조 표시는 시기를 결정 합니다.  
  
 Rich edit 컨트롤의 현재 선택 영역을 확인 하려면 사용 하 여는 [GetSel](../mfc/reference/cricheditctrl-class.md#getsel) 멤버 함수입니다. 현재 선택 영역을 설정 하려면는 [SetSel](../mfc/reference/cricheditctrl-class.md#setsel) 멤버 함수입니다. [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 구조는 문자의 범위를 지정 하려면 이러한 함수와 함께 사용 합니다. 현재 선택 항목의 내용에 대 한 정보를 검색 하려면 사용할 수 있습니다는 [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) 멤버 함수입니다.  
  
 기본적으로 rich edit 컨트롤이 표시 하 고 얻거나 포커스를 잃을 때 강조 표시 선택 영역이 숨깁니다. 표시 하거나 사용 하 여 언제 든 지 강조 표시 선택 영역이 숨길 수 있습니다는 [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) 멤버 함수입니다. 예를 들어 응용 프로그램 rich edit 컨트롤에서 텍스트를 찾으려면 검색 대화 상자를 제공할 수 있습니다. 응용 프로그램 대화 상자를 닫지 않고 일치 하는 텍스트를 선택할 수, 사용 해야 하며이 경우 `HideSelection` 선택 영역을 강조 표시 합니다.  
  
 Rich edit 컨트롤에서 선택한 텍스트를 가져오려면는 [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) 멤버 함수입니다. 텍스트는 지정 된 문자 배열에 복사 됩니다. 배열이 선택한 텍스트와 null 종결 문자를 포함할 수 있는 크기를 확인 해야 합니다.  
  
 사용 하 여 서식 있는 편집 컨트롤에서 문자열을 검색할 수 있습니다는 [FindText](../mfc/reference/cricheditctrl-class.md#findtext) 멤버 함수는 [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) 이 함수를 사용 하는 구조를 검색 및을 검색할 문자열 텍스트 범위를 지정 합니다. 검색은 대/소문자 구분 여부와 같은 옵션을 지정할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

