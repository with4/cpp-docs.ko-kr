---
title: "Rich Edit 컨트롤의 클립보드 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클립보드, CRichEditCtrl의 작업"
  - "rich edit 컨트롤의 복사 작업"
  - "CRichEditCtrl 클래스, 클립보드 작업"
  - "CRichEditCtrl 클래스, 붙여넣기 작업"
  - "CRichEditCtrl 클래스의 잘라내기 작업"
  - "클립보드 데이터 붙여넣기"
  - "rich edit 컨트롤, 클립보드 작업"
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Rich Edit 컨트롤의 클립보드 작업
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용 프로그램은 최상의 이용할 수 있는 클립보드 형식 또는 특정 클립보드 형식 중 하나를 사용하여 여러 편집 컨트롤으로 클립보드의 내용을 붙여넣을 수 있습니다. \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\)  여러 편집 컨트롤이 클립보드 형식을 붙여넣을 수 있는지 여부를 확인할 수 있습니다.  
  
 [Copy](../Topic/CRichEditCtrl::Copy.md) 또는 [Cut](../Topic/CRichEditCtrl::Cut.md) 멤버 함수를 사용하여 현재 선택된 내용을 복사하거나 잘라낼 수 있습니다.  마찬가지로, [Paste](../Topic/CRichEditCtrl::Paste.md) 멤버 함수를 사용하여 여러 편집 컨트롤로 클립보드의 내용을 붙여넣을 수 있습니다.  컨트롤은 가장 설명적인 형식을 인식하고, 사용 가능한 첫 번째 형식을 붙여넣습니다.  
  
 특정 클립보드 형식을 붙여넣기 위해, [PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md) 멤버 함수를 사용할 수 있습니다.  이 기능은 사용자가 클립보드 형식을 선택할 수 있도록 특별한 붙여넣기 명령어를 사용하여 응용프로그램들에서 유용하게 사용됩니다.  주어진 형식이 컨트롤에서 인식될 수 있는지 여부를 결정하기 위해 [CanPaste](../Topic/CRichEditCtrl::CanPaste.md) 멤버 함수를 사용할 수 있습니다.  
  
 또한 모든 이용할 수 있는 클립보드 형식이 여러 편집 컨트롤에 의해 인식될 수 있는지 여부를 결정하기위해 `CanPaste` 를 사용할 수 있습니다.  이 기능은 `OnInitMenuPopup` 처리기에서 유용합니다.  응용 프로그램은 컨트롤이 모든 이용할 수 있는 형식을 붙여넣기 할 수 있는지 여부에 따라 이것의 붙여넣기 명령을 활성화할 수 있습니다.  
  
 여러 편집 컨트롤들은 두 클립보드 서식들을 등록합니다. 여러 텍스트 형식과 RichEdit 텍스트와 객체들로 불리는 형식.  응용 프로그램을 **CF\_RTF** 와 **CF\_RETEXTOBJ** 값들을 지정하는 [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수를 사용하여 이러한 형식들을 등록할 수 있습니다.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)