---
title: "Rich Edit 컨트롤의 현재 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl 클래스, 현재 선택 내용"
  - "CRichEditCtrls의 현재 선택 내용"
  - "rich edit 컨트롤, 현재 선택 내용"
  - "선택, CRichEditCtrl의 현재"
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rich Edit 컨트롤의 현재 선택
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The user can select text in a rich edit control \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) by using the mouse or the keyboard.  The current selection is the range of selected characters, or the position of the insertion point if no characters are selected.  An application can get information about the current selection, set the current selection, determine when the current selection changes, and show or hide the selection highlight.  
  
 To determine the current selection in a rich edit control, use the [GetSel](../Topic/CRichEditCtrl::GetSel.md) member function.  To set the current selection, use the [SetSel](../Topic/CRichEditCtrl::SetSel.md) member function.  The [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) structure is used with these functions to specify a range of characters.  To retrieve information about the contents of the current selection, you can use the [GetSelectionType](../Topic/CRichEditCtrl::GetSelectionType.md) member function.  
  
 By default, a rich edit control shows and hides the selection highlight when it gains and loses the focus.  You can show or hide the selection highlight at any time by using the [HideSelection](../Topic/CRichEditCtrl::HideSelection.md) member function.  For example, an application might provide a Search dialog box to find text in a rich edit control.  The application might select matching text without closing the dialog box, in which case it must use `HideSelection` to highlight the selection.  
  
 To get the selected text in a rich edit control, use the [GetSelText](../Topic/CRichEditCtrl::GetSelText.md) member function.  The text is copied to the specified character array.  You must ensure that the array is large enough to hold the selected text plus a terminating null character.  
  
 You can search for a string in a rich edit control by using the [FindText](../Topic/CRichEditCtrl::FindText.md) member function The [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) structure used with this function specifies the text range to search and the string to search for.  You can also specify such options as whether the search is case\-sensitive.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)