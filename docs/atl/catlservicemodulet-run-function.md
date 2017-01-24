---
title: "CAtlServiceModuleT::Run Function | Microsoft Docs"
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
  - "CServiceModule::Run"
  - "CServiceModule.Run"
  - "CSecurityDescriptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 서비스, 보안"
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Run Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Run** contains calls to `PreMessageLoop`, `RunMessageLoop`, and `PostMessageLoop`.  호출 된 후 `PreMessageLoop` 먼저 서비스의 스레드 ID를 저장 합니다.  이 ID를 사용 하는 전송 하 여 자체적으로 닫힐 수 서비스는  **WM\_QUIT** 는 Win32 API 함수를 사용 하 여 메시지  [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop`그런 다음 호출 `InitializeSecurity`.  기본적으로 `InitializeSecurity` 전화  [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) NULL로 설정 하는 보안 설명자는 모든 사용자 개체에 액세스할 수 있습니다.  
  
 서비스 자체의 보안을 지정 하지 않을 경우 재정의 `PreMessageLoop` 호출 하 고 `InitializeSecurity`, COM 다음 레지스트리에서 보안 설정을 확인 합니다.  레지스트리 설정을 구성 하는 편리한 방법을 사용 되는  [DCOMCNFG](../atl/dcomcnfg.md) 나중에이 섹션에서 설명 하는 유틸리티.  
  
 보안이 지정 되 면 새 클라이언트 프로그램에 연결할 수 있도록 개체를 COM에 등록 됩니다.  마지막으로 프로그램 실행 및 프로그램 메시지 루프를 입력 합니다. 서비스 제어 관리자 \(SCM\)를 알려줍니다.  서비스를 종료할 때 종료 메시지를 게시할 때까지 프로그램이 계속 실행 됩니다.  
  
## 참고 항목  
 [서비스](../atl/atl-services.md)   
 [CSecurityDesc Class](../atl/reference/csecuritydesc-class.md)   
 [CSid Class](../atl/reference/csid-class.md)   
 [CDacl Class](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)