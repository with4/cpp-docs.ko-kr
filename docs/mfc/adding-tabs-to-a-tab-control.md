---
title: "탭 컨트롤에 탭 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CTabCtrl 클래스, 탭 추가"
  - "CTabCtrl에 탭 배치"
  - "tab 컨트롤, 탭 추가"
  - "탭, CTabCtrl 클래스에 추가"
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 탭 컨트롤에 탭 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

After creating the tab control \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\), add as many tabs as you need.  
  
### To add a tab item  
  
1.  Prepare a [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure.  
  
2.  Call [CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md), passing the structure.  
  
3.  Repeat steps 1 and 2 for additional tab items.  
  
 For more information, see [Creating a Tab Control](http://msdn.microsoft.com/library/windows/desktop/bb760550) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)