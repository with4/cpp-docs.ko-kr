---
title: "방법: MFC 응용 프로그램에서 리본 리소스 로드 | Microsoft Docs"
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
  - "리본 리소스, 로드"
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: MFC 응용 프로그램에서 리본 리소스 로드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

응용프로그램에서 리본 리소스를 사용하기 위해 리본 리소스를 로드하려면 응용프로그램을 수정합니다.  
  
### 리본 리소스를 로드 하려면  
  
1.  `CMainFrame` 클래스에서 `Ribbon Control` 개체를 선언합니다.  
  
    ```  
    CMFCRibbonBar m_wndRibbonBar;   
    ```  
  
2.  `CMainFrame::OnCreate` 에서, 리본 컨트롤을 만들고 초기화합니다.  
  
    ```  
    if (!m_wndRibbonBar.Create (this))  
    {  
        return -1;  
    }  
  
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
    {  
        return -1;  
    }  
    ```  
  
## 참고 항목  
 [리본 디자이너\(MFC\)](../mfc/ribbon-designer-mfc.md)