---
title: "Running the Program as a Local Server | Microsoft Docs"
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
  - "ATL 서비스, running as local servers"
  - "디버깅[ATL], running services as local server"
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Running the Program as a Local Server
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램을 서비스로 실행 하는 것이 편리 하지 않으면 프로그램이 표준 로컬 서버로 실행 되도록 레지스트리를 일시적으로 변경할 수 있습니다.  단순히 이름 바꾸기는 `LocalService` 해당 AppID 값 `_LocalService` 하 고는 `LocalServer32` 키 아래에 CLSID 올바르게 설정.  \(참고 DCOMCNFG를 사용 하 여 응용 프로그램을 다른 컴퓨터에서 실행 되도록 지정 하는 변경 하면 `LocalServer32` 키를 `_LocalServer32`.\) 때문에 몇 초 동안 시작 시 로컬 서버를 취하는 프로그램 실행 호출을  **StartServiceCtrlDispatcher** 에서 `CAtlServiceModuleT::Start` 실패 하기 전에 몇 초 정도 걸립니다.  
  
## 참고 항목  
 [Debugging Tips](../atl/debugging-tips.md)