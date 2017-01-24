---
title: "ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 응용 프로그램에 컨트롤 삽입 | Microsoft Docs"
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
  - "ActiveX 컨트롤 컨테이너[C++], 컨트롤 삽입"
  - "ActiveX 컨트롤[C++], 프로젝트에 추가"
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX 컨트롤 컨테이너: 컨트롤 컨테이너 응용 프로그램에 컨트롤 삽입
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Before you can access an ActiveX control from an ActiveX control container application, you must add the ActiveX control to the container application using the [Insert ActiveX Control](../mfc/insert-activex-control-dialog-box.md) dialog box.  
  
 To add an ActiveX control to the ActiveX control container project, see [Viewing and Adding ActiveX Controls to a Dialog Box](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Once you add the control, you need to add a member variable \(of the ActiveX control type\) to the dialog box class.  For more information on this procedure, see [Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Once you have added the member variable a class, referred to as a wrapper class, is automatically generated and added to your project.  This class is used as an interface between the control container and the embedded control.  
  
## 참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)