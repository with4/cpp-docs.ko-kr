---
title: "프레임워크를 기반으로 구축 | Microsoft Docs"
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
  - "응용 프로그램 프레임워크[C++], 응용 프로그램 빌드"
  - "응용 프로그램[MFC]"
  - "응용 프로그램 관련 클래스[C++]"
  - "MFC[C++], 응용 프로그램 개발"
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임워크를 기반으로 구축
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Your role in configuring an application with the MFC framework is to supply the application\-specific source code and to connect the components by defining what messages and commands to which they respond.  You use the C\+\+ language and standard C\+\+ techniques to derive your own application\-specific classes from those supplied by the class library and to override and augment the base class's behavior.  
  
 In related topics, the following tables describe the general sequence of operations you will typically follow and your responsibilities versus the framework's responsibilities:  
  
-   [Sequence for Building an Application with the Framework](../mfc/sequence-of-operations-for-building-mfc-applications.md)  
  
-   [OLE 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)  
  
-   [ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)  
  
-   [데이터베이스 응용 프로그램을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-database-applications.md)  
  
 For the most part, you can follow these tables as a sequence of steps for creating an MFC application, although some of the steps are alternative options.  For example, most applications use one type of view class from the several types available.  
  
## 참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)