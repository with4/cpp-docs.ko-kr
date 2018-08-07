---
title: 'Catlservicemodulet:: Servicemain 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs:
- C++
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dff3fa3f3ed20406955570f2ad72531f4e44f11
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848123"
---
# <a name="catlservicemoduletservicemain-function"></a>Catlservicemodulet:: Servicemain 함수
서비스 제어 관리자 (SCM) 호출 `ServiceMain` 서비스 제어판 응용 프로그램을 열면 서비스를 선택 하 고 클릭 **시작**합니다.  
  
 호출 후 SCM `ServiceMain`, 서비스는 SCM 처리기 함수를 제공 해야 합니다. 이 함수를 사용 하면 서비스의 상태를 가져오고 (예: 일시 중지 또는 중지) 특정 지침을 전달 하는 SCM이 있습니다. SCM 서비스에 전달 하는 경우이 함수를 가져옵니다 `_Handler` Win32 API 함수 [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054)합니다. (`_Handler` 비정적 멤버 함수를 호출 하는 정적 멤버 함수인 [처리기](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 시작 시 서비스를 SCM 현재 상태에 알려야 합니다. SERVICE_START_PENDING Win32 API 함수에 전달 하 여 이렇게 [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241)합니다.  
  
 `ServiceMain` 그런 다음 호출 `CAtlExeModuleT::InitializeCom`, Win32 API 함수를 호출 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)합니다. 기본적으로 `InitializeCom` COINIT_MULTITHREADED 플래그 함수에 전달 합니다. 이 플래그는 자유 스레드된 서버로 프로그램 임을 나타냅니다.  
  
 이제 `CAtlServiceModuleT::Run` 서비스의 기본 작업을 수행 하기 위해 호출 됩니다. `Run` 서비스가 중지 될 때까지 실행을 계속 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)   
 [Catlservicemodulet:: Servicemain](../atl/reference/catlservicemodulet-class.md#servicemain)

