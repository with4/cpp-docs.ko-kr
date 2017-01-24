---
title: "MFC DLL에서 사용할 수 없는 MFC 클래스 또는 함수가 있습니까? | Microsoft Docs"
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
  - "DLL[C++], MFC"
  - "DLL[C++], 제한 사항"
  - "MFC DLL[C++], 제한 사항"
ms.assetid: 18e2f1cb-4f72-4d3a-a951-3488208872c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC DLL에서 사용할 수 없는 MFC 클래스 또는 함수가 있습니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

확장 DLL은 클라이언트 응용 프로그램의 `CWinApp` 파생 클래스를 사용하며  자체의 `CWinApp` 파생 클래스를 가질 수 없습니다.  
  
 기본 DLL에는 MFC 응용 프로그램과 마찬가지로, `CWinApp` 파생 클래스 및 해당 응용 프로그램 클래스의 단일 개체가 있어야 합니다.  그러나 응용 프로그램의 `CWinApp` 개체와 달리 DLL의 `CWinApp` 개체에는 기본 메시지 펌프가 없습니다.  
  
 `CWinApp::Run` 메커니즘은 DLL에 적용되지 않으므로 기본 메시지 펌프는 응용 프로그램에서 소유합니다.  DLL에서 모덜리스 대화 상자를 열거나 자체의 기본 프레임 창을 갖는 경우, 응용 프로그램의 기본 메시지 펌프는 DLL에서 내보내는 루틴을 호출해야 합니다. 그러면 이 루틴이 DLL의 응용 프로그램 개체에 대한 `CWinApp::PreTranslateMessage` 멤버 함수를 호출하게 됩니다.  
  
## 참고 항목  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)