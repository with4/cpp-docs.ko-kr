---
title: "CAtlServiceModuleT::ServiceMain Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceMain"
  - "CServiceModule::ServiceMain"
  - "CServiceModule.ServiceMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ServiceMain method"
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::ServiceMain Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

서비스 제어 관리자 \(SCM\)를 호출 합니다. `ServiceMain` 서비스 제어판 응용 프로그램을 열 때 해당 서비스를 선택한 다음  **시작**.  
  
 SCM 후 호출 `ServiceMain`, 서비스 SCM 처리기 함수를 제공 해야 합니다.  이 함수는 SCM을 서비스의 상태 및 일시 중지 또는 중지와 같은 특정 지침을 전달할 수 있습니다.  SCM 서비스 전달 될 때이 함수를 가져옵니다  **\_Handler** Win32 API 함수에  [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054).  \(**\_Handler** 정적 멤버 함수가 비정적 멤버 함수를 호출 된  [처리기](../atl/catlservicemodulet-handler-function.md).\)  
  
 시작 시 서비스 또한 SCM의 현재 상태를 알려야 합니다.  전달 하 여이 작업을 수행  **SERVICE\_START\_PENDING** Win32 API 함수에  [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain`그런 다음 호출 `CAtlExeModuleT::InitializeCom`, Win32 API 함수를 호출 하는  [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279).  기본적으로 `InitializeCom` 전달 된  **COINIT\_MULTITHREADED** 플래그를 함수.  이 플래그는 프로그램이 자유 스레드된 서버 임을 나타냅니다.  
  
 이제 `CAtlServiceModuleT::Run` 서비스의 기본 작업을 수행 하기 위해 호출 됩니다.  **실행** 이 서비스를 중지할 때까지 실행을 계속 합니다.  
  
## 참고 항목  
 [서비스](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)