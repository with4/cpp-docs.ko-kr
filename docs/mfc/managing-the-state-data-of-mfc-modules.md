---
title: "MFC 모듈의 상태 데이터 관리 | Microsoft Docs"
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
  - "데이터 관리[C++]"
  - "데이터 관리[C++], MFC 모듈"
  - "내보낸 인터페이스 및 전역 상태[C++]"
  - "전역 상태[C++]"
  - "MFC[C++], 상태 데이터 관리"
  - "모듈 상태 복원됨"
  - "모듈 상태, 저장 및 복원"
  - "여러 모듈"
  - "창 프로시저 진입점[C++]"
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MFC 모듈의 상태 데이터 관리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article discusses the state data of MFC modules and how this state is updated when the flow of execution \(the path code takes through an application when executing\) enters and leaves a module.  Switching module states with the `AFX_MANAGE_STATE` and `METHOD_PROLOGUE` macros is also discussed.  
  
> [!NOTE]
>  The term "module" here refers to an executable program, or to a DLL \(or set of DLLs\) that operate independently of the rest of the application, but uses a shared copy of the MFC DLL.  An ActiveX control is a typical example of a module.  
  
 As shown in the following figure, MFC has state data for each module used in an application.  Examples of this data include Windows instance handles \(used for loading resources\), pointers to the current `CWinApp` and `CWinThread` objects of an application, OLE module reference counts, and a variety of maps that maintain the connections between Windows object handles and corresponding instances of MFC objects.  However, when an application uses multiple modules, the state data of each module is not application wide.  Rather, each module has its own private copy of the MFC's state data.  
  
 ![단일 모듈 상태 데이터&#40;응용 프로그램&#41;](../mfc/media/vc387n1.png "vc387N1")  
단일 모듈\(응용 프로그램\)의 상태 데이터  
  
 A module's state data is contained in a structure and is always available via a pointer to that structure.  When the flow of execution enters a particular module, as shown in the following figure, that module's state must be the "current" or "effective" state.  Therefore, each thread object has a pointer to the effective state structure of that application.  Keeping this pointer updated at all times is vital to managing the application's global state and maintaining the integrity of each module's state.  Incorrect management of the global state can lead to unpredictable application behavior.  
  
 ![여러 모듈 상태 데이터](../mfc/media/vc387n2.png "vc387N2")  
여러 모듈의 상태 데이터  
  
 In other words, each module is responsible for correctly switching between module states at all of its entry points.  An "entry point" is any place where the flow of execution can enter the module's code.  Entry points include:  
  
-   [Exported functions in a DLL](../mfc/exported-dll-function-entry-points.md)  
  
-   [Member functions of COM interfaces](../mfc/com-interface-entry-points.md)  
  
-   [Window procedures](../mfc/window-procedure-entry-points.md)  
  
## 참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)