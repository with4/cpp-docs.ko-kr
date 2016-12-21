---
title: "Using the RichEdit 1.0 Control with MFC | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "RichEdit 1.0 control"
  - "rich edit controls, RichEdit 1.0"
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using the RichEdit 1.0 Control with MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RichEdit 컨트롤을 사용하려면 먼저 [AfxInitRichEdit2](../Topic/AfxInitRichEdit2.md)를 호출하여 RichEdit 2.0 컨트롤\(RICHED20.DLL\)을 로드하거나 [AfxInitRichEdit](../Topic/AfxInitRichEdit.md)를 호출하여 이전의 RichEdit 1.0 컨트롤\(RICHED32.DLL\)을 로드해야 합니다.  
  
 현재 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 클래스와 이전의 RichEdit 1.0 컨트롤을 동시에 사용할 수도 있지만, **CRichEditCtrl**은 RichEdit 2.0 컨트롤만 지원하도록 디자인되었습니다.  RichEdit 1.0과 RichEdit 2.0은 상당히 유사하기 때문에 대부분의 메서드가 작동하지만, 1.0 컨트롤과 2.0 컨트롤 간에는 몇 가지 차이점이 있으므로 일부 메서드가 작동하지 않거나 오작동할 수도 있습니다.  
  
## 요구 사항  
 MFC  
  
## 참고 항목  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)