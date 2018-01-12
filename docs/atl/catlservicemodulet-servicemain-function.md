---
title: "CAtlServiceModuleT::ServiceMain 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs: C++
helpviewer_keywords: ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 633e9bc4689ced93e1c22151b32654f7ae9d7ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT::ServiceMain 함수
서비스 제어 관리자 (SCM) 호출 `ServiceMain` 서비스 제어판 응용 프로그램을 열 때 서비스를 선택 하 고 클릭 **시작**합니다.  
  
 SCM 후 호출 `ServiceMain`, 서비스의 SCM 처리기 함수를 지정 해야 합니다. 이 함수에는 SCM을 (예: 일시 중지 또는 중지) 특정 지침을 전달 하 고 서비스의 상태를 가져올 수 있습니다. SCM에서 서비스에 전달 될 때이 함수를 가져옵니다 **_Handler** Win32 API 함수에 [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054)합니다. (**_Handler** 비정적 멤버 함수를 호출 하는 정적 멤버 함수 [처리기](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 시작 시 서비스를 현재 상태로 SCM 알려야 합니다. 전달 하 여 이렇게 **고 있습니다 SERVICE_START_PENDING** Win32 API 함수에 [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241)합니다.  
  
 `ServiceMain`그런 다음 호출 `CAtlExeModuleT::InitializeCom`, Win32 API 함수를 호출 하 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)합니다. 기본적으로 `InitializeCom` 전달는 **COINIT_MULTITHREADED** 함수에 대 한 플래그입니다. 이 플래그를 자유 스레드 서버로 프로그램 임을 나타냅니다.  
  
 이제 `CAtlServiceModuleT::Run` 서비스의 주요 작업을 수행 하기 위해 호출 됩니다. **실행** 서비스가 중지 될 때까지 계속 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

