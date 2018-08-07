---
title: 'Catlservicemodulet:: Run 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e509ad88a744f6ebaaca41ecd0d6455d68c2585c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850656"
---
# <a name="catlservicemoduletrun-function"></a>Catlservicemodulet:: Run 함수
`Run` 에 대 한 호출을 포함 `PreMessageLoop`하십시오 `RunMessageLoop`, 및 `PostMessageLoop`합니다. 호출 된 후 `PreMessageLoop` 먼저 저장 서비스의 스레드 id입니다. 서비스는 Win32 API 함수를 사용 하 여 WM_QUIT 메시지를 보내 자체를 닫으려면이 ID를 사용 하는 [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946)합니다.  
  
 `PreMessageLoop` 그런 다음 호출 `InitializeSecurity`합니다. 기본적으로 `InitializeSecurity` 호출 [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) NULL로 설정 하는 보안 설명자를 사용 하 여는 것을 의미 하는 모든 사용자가 개체에 대 한 액세스.  
  
 서비스는 자체 보안을 지정 하지 않으려면 재정의 `PreMessageLoop` 호출 하지 `InitializeSecurity`, COM 레지스트리 보안 설정을 확인 한 다음 됩니다. 레지스트리 설정을 구성 하는 편리한 방법이 된 합니다 [DCOMCNFG](../atl/dcomcnfg.md) 이 섹션의 뒷부분에서 설명 하는 유틸리티입니다.  
  
 보안 지정 되 면 개체는 새 클라이언트 프로그램에 연결할 수 있도록 COM에 등록 됩니다. 마지막으로 프로그램 실행을 프로그램 메시지 루프를 입력 합니다. 서비스 제어 관리자 (SCM)을 지시 합니다. 서비스 종료 시 종료 메시지를 게시 될 때까지 프로그램이 계속 실행 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)   
 [CSecurityDesc 클래스](../atl/reference/csecuritydesc-class.md)   
 [CSid 클래스](../atl/reference/csid-class.md)   
 [CDacl 클래스](../atl/reference/cdacl-class.md)   
 [Catlservicemodulet:: Run](../atl/reference/catlservicemodulet-class.md#run)

