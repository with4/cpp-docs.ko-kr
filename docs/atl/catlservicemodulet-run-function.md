---
title: "CAtlServiceModuleT::Run 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ff3efe9298b7a2c11e7f83ef58640b2947519b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT::Run 함수
**실행** 에 대 한 호출을 포함 `PreMessageLoop`, `RunMessageLoop`, 및 `PostMessageLoop`합니다. 호출 된 후 `PreMessageLoop` 먼저 서비스의 스레드 ID를 저장 합니다. 서비스에서이 ID를 전송 하 여 자체를 닫으려면 사용할는 **WM_QUIT** Win32 API 함수를 사용 하 여 메시지 [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946)합니다.  
  
 `PreMessageLoop`그런 다음 호출 `InitializeSecurity`합니다. 기본적으로 `InitializeSecurity` 호출 [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) 하 여 NULL로 설정의 보안 설명자를 의미 하는 모든 사용자의 개체에 대 한 액세스.  
  
 서비스를 자체 보안을 지정 하지 않으려면 하는 경우 재정의 `PreMessageLoop` 을 `InitializeSecurity`, COM 됩니다 확인 한 다음 레지스트리에서 보안 설정 합니다. 레지스트리 설정을 구성 하는 편리한 방법은 인는 [DCOMCNFG](../atl/dcomcnfg.md) 이 섹션의 뒷부분에서 설명 하는 유틸리티입니다.  
  
 보안이 지정 되 면 새 클라이언트 프로그램에 연결할 수 있도록 COM에 등록 됩니다. 마지막으로 프로그램 실행 및 프로그램 메시지 루프를 입력 합니다. 서비스 제어 관리자 (SCM 에) 지시 합니다. 서비스 종료 시 종료 메시지를 게시 될 때까지 프로그램 실행 중인 상태로 유지 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)   
 [CSecurityDesc 클래스](../atl/reference/csecuritydesc-class.md)   
 [CSid 클래스](../atl/reference/csid-class.md)   
 [CDacl 클래스](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

