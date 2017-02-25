---
title: "대화 상자 편집기를 사용하여 컨트롤 추가 | Microsoft Docs"
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
  - "공용 컨트롤[C++], 추가"
  - "컨트롤[MFC], 대화 상자에 추가"
  - "대화 상자 컨트롤[C++], 대화 상자에 추가"
  - "대화 상자 편집기, 컨트롤 만들기"
  - "Windows 공용 컨트롤[C++], 추가"
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 대화 상자 편집기를 사용하여 컨트롤 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you create your dialog\-template resource with the [dialog editor](../mfc/dialog-editor.md), you drag controls from a controls palette and drop them into the dialog box.  This adds the specifications for that control type to the dialog\-template resource.  When you construct a dialog object and call its **Create** or `DoModal` member function, the framework creates a Windows control and places it in the dialog window on screen.  
  
 You can instead [create controls by hand](../mfc/adding-controls-by-hand.md) if you want.  This is more work.  
  
## 참고 항목  
 [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)   
 [컨트롤](../mfc/controls-mfc.md)