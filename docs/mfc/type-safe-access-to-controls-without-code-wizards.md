---
title: "코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행 | Microsoft Docs"
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
  - "대화 상자 컨트롤, 액세스"
  - "대화 상자, 컨트롤 액세스"
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The first approach to creating type\-safe access to controls uses an inline member function to cast the return type of class `CWnd`'s `GetDlgItem` member function to the appropriate C\+\+ control type, as in this example:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 You can then use this member function to access the control in a type\-safe manner with code similar to the following:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## 참고 항목  
 [대화 상자의 컨트롤에 대한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행](../mfc/type-safe-access-to-controls-with-code-wizards.md)