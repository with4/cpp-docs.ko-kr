---
title: "마법사 역할을 하는 속성 시트 | Microsoft Docs"
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
  - "속성 시트, 마법사"
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 역할을 하는 속성 시트
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A key characteristic of a wizard property sheet is that navigation is provided with Next or Finish, Back, and Cancel buttons instead of tabs.  You need to call [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) before calling [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) on the property sheet object to take advantage of this feature.  
  
 The user receives the same [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md) and [CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md) notifications while moving from one page to another page.  Next and Finish buttons are mutually exclusive controls; that is, only one of them will be shown at a time.  On the first page, the Next button should be enabled.  If the user is on the last page, the Finish button should be enabled.  This is not done automatically by the framework.  You have to call [CPropertySheet::SetWizardButton](../Topic/CPropertySheet::SetWizardButtons.md) on the last page to achieve this.  
  
 To display all of the default buttons, you mush show the Finish button and move the Next button.  Then move the Back button so that its relative position to the Next button is maintained.  For more explanation, search for KB article Q143210.  Knowledge Base articles are available in the MSDN Library.  
  
## 예제  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/CPP/property-sheets-as-wizards_1.cpp)]  
  
## 참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)