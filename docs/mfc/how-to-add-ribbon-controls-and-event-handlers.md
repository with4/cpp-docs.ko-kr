---
title: "방법: 리본 컨트롤 및 이벤트 처리기 추가 | Microsoft Docs"
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
  - "이벤트 처리기, 추가"
  - "리본 컨트롤, 추가"
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 리본 컨트롤 및 이벤트 처리기 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ribbon controls are elements, such as buttons and combo boxes, that you add to panels.  Panels are areas of the ribbon bar that display a group of related controls.  
  
 In this topic, you will open the Ribbon Designer, add a button, and then link an event that displays "Hello World".  
  
### To open the Ribbon Designer  
  
1.  In Visual Studio, on the **View** menu, click **Resource View**.  
  
2.  In **Resource View**, double\-click the ribbon resource to display it on the design surface.  
  
### To add a Button and an Event Handler  
  
1.  From the **Toolbar**, click **Button** and drag it on to a panel in the design surface.  
  
2.  Right\-click the button, and click **Add Event Handler**.  
  
3.  In the **Event Handler Wizard**, confirm the default settings and click **Add and Edit**.  자세한 내용은 [이벤트 처리기 마법사](../ide/event-handler-wizard.md)을 참조하십시오.  
  
4.  In the code editor, add the following code into the handler function:  
  
    ```  
    MessageBox((LPCTSTR)L"Hello World");  
    ```  
  
## 참고 항목  
 [RibbonGadgets 샘플: 리본 가젯 응용 프로그램](../top/visual-cpp-samples.md)   
 [리본 디자이너\(MFC\)](../mfc/ribbon-designer-mfc.md)