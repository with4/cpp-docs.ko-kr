---
title: 클립보드 작업에서 서식 있는 편집 컨트롤 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e831a76a491d1025ae45117d40362a85523742da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341286"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Rich Edit 컨트롤의 클립보드 작업
응용 프로그램를 서식 있는 편집 컨트롤로 클립보드의 내용을 붙여 넣을 수 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 사용 가능한 최상의 클립보드 형식 또는 특정 클립보드 형식을 사용 하 여 합니다. 또한 서식 있는 편집 컨트롤에서 클립보드 형식 붙여넣기가 지원되는지 여부도 확인할 수 있습니다.  
  
 복사 하거나 사용 하 여 현재 선택 항목의 내용을 잘라낼 수 있습니다는 [복사](../mfc/reference/cricheditctrl-class.md#copy) 또는 [잘라내기](../mfc/reference/cricheditctrl-class.md#cut) 멤버 함수입니다. 사용 하 여 서식 있는 편집 컨트롤로 클립보드의 내용을 붙여넣을 수는 마찬가지로,는 [붙여](../mfc/reference/cricheditctrl-class.md#paste) 멤버 함수입니다. 컨트롤은 처음으로 인식되는 첫 번째 사용 가능한 형식을 가장 설명적인 형식으로 인지하고 이를 붙여넣습니다.  
  
 특정 클립보드 형식을 붙여넣으려면를 사용할 수 있습니다는 [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) 멤버 함수입니다. 이 함수는 사용자가 클립보드 형식을 선택할 수 있게 해주는 선택하여 붙여넣기 명령이 있는 응용 프로그램에서 유용합니다. 사용할 수는 [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) 멤버 함수를 특정된 형식이 컨트롤에서 인식 되는지 여부를 확인 합니다.  
  
 또한 `CanPaste`를 사용하면 사용 가능한 클립보드 형식이 서식 있는 편집 컨트롤에서 인식되는지 여부를 확인할 수 있습니다. 이 기능은 `OnInitMenuPopup` 처리기에서 유용합니다. 응용 프로그램은 컨트롤이 모든 사용 가능한 형식을 붙여넣을 수 있는지 여부에 따라 해당 붙여넣기 명령을 활성화하거나 회색으로 표시할 수 있습니다.  
  
 서식 있는 편집 컨트롤은 복합 텍스트 형식과 RichEdit 텍스트 및 개체라고 부르는 형식의 두 가지 클립보드 형식을 등록합니다. 응용 프로그램 사용 하 여 이러한 형식을 등록할 수는 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수를 지정 하는 **CF_RTF** 및 **CF_RETEXTOBJ** 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

