---
title: "CAtlServiceModuleT::Start Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule.Start"
  - "CServiceModule::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start 메서드"
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Start Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

서비스가 실행 되 면  **\_tWinMain** 전화  **CAtlServiceModuleT::WinMain**를 차례로 호출 `CAtlServiceModuleT::Start`.  
  
 `CAtlServiceModuleT::Start`설정의 배열  **SERVICE\_TABLE\_ENTRY** 구조는 각 서비스의 시작 함수에 매핑해야 합니다.  이 배열은 다음 Win32 API 함수에 전달 됩니다  [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324).  이론적으로 하나의 EXE 여러 서비스를 처리할 수 및 배열에 여러 가질 수  **SERVICE\_TABLE\_ENTRY** 구조.  현재, ATL 생성 서비스는 EXE 마다 하나의 서비스를 지원합니다.  따라서 서비스 이름을 포함 하는 단일 항목 배열을 포함 하 고  **\_ServiceMain** 함수로 시작.  **\_ServiceMain** 의 정적 멤버 함수는 `CAtlServiceModuleT` 는 비정적 멤버 함수를 호출 하는 `ServiceMain`.  
  
> [!NOTE]
>  실패의  **StartServiceCtrlDispatcher** 서비스 제어에 연결 하려면 관리자 \(SCM\) 아마도 프로그램이 서비스로 실행 되 고 있습니다.  이 경우 호출 프로그램 `CAtlServiceModuleT::Run` 직접 로컬 서버로 프로그램을 실행할 수 있습니다.  로컬 서버로 프로그램 실행에 대 한 자세한 내용은  [디버깅 팁](../atl/debugging-tips.md).  
  
## 참고 항목  
 [서비스](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)