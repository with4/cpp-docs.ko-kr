---
title: "ActiveX 컨트롤을 만드는 작업 시퀀스 | Microsoft Docs"
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
  - "ActiveX 컨트롤[C++], 만들기"
  - "MFC ActiveX 컨트롤[C++], 만들기"
  - "OLE 컨트롤[C++], MFC"
  - "시퀀스[C++]"
  - "시퀀스[C++], ActiveX 컨트롤 만들기"
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX 컨트롤을 만드는 작업 시퀀스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The following table shows your role and the framework's role in creating ActiveX controls \(formerly known as OLE controls\).  
  
### Creating ActiveX Controls  
  
|Task|You do|The framework does|  
|----------|------------|------------------------|  
|Create an ActiveX control framework.|Run the MFC ActiveX Control Wizard to create your control.  Specify the options you want in the options pages.  Options include the type and name of the control in the project, licensing, subclassing, and an About Box method.|The MFC ActiveX Control Wizard creates the files for an ActiveX control with basic functionality, including source files for your application, control, and property page or pages; a resource file; a project file; and others, all tailored to your specifications.|  
|See what the control and the ActiveX Control Wizard offer without adding a line of your own code.|Build the ActiveX control and test it with Internet Explorer or the [TSTCON sample](../top/visual-cpp-samples.md).|The running control has the ability to be resized and moved.  It also has an **About Box** method \(if chosen\) that can be invoked.|  
|Implement the control's methods and properties.|Implement your control\-specific methods and properties by adding member functions to provide an exposed interface to the control's data.  Add member variables to hold data structures and use event handlers to fire events when you determine.|The framework has already defined a map to support the control's events, properties, and methods, leaving you to focus on how the properties and methods are implemented.  The default property page is viewable and a default About Box method is supplied.|  
|Construct the control's property page or pages.|Use the Visual C\+\+ resource editors to visually edit the control's property page interface:<br /><br /> -   Create additional property pages.<br />-   Create and edit bitmaps, icons, and cursors.<br /><br /> You can also test the property page\(s\) in the dialog editor.|The default resource file created by the MFC Application Wizard supplies many of the resources you need.  Visual C\+\+ lets you edit existing resources and add new resources easily and visually.|  
|Test the control's events, methods, and properties.|Rebuild the control and use Test Container to test that your handlers work correctly.|You can invoke the control's methods and manipulate its properties through the property page interface or through Test Container.  In addition, use Test Container to track events fired from the control and notifications received by the control's container.|  
  
## 참고 항목  
 [프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)   
 [MFC 응용 프로그램을 빌드하는 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [데이터베이스 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-database-applications.md)