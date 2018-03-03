---
title: "CAtlServiceModuleT::Start 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d4ee7899cda213bf8d8cfd529fd7609976e20d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT::Start 함수
서비스를 실행할 때 **_tWinMain** 호출 **CAtlServiceModuleT::WinMain**를 호출 하 `CAtlServiceModuleT::Start`합니다.  
  
 `CAtlServiceModuleT::Start`배열을 설정 **SERVICE_TABLE_ENTRY** 각 서비스는 시작 함수에 매핑하는 구조입니다. Win32 API 함수에 전달 된이 배열 다음 [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324)합니다. 이론적으로, 한 EXE 여러 서비스를 처리할 수 및 배열에는 여러 개 있을 수 **SERVICE_TABLE_ENTRY** 구조입니다. 그러나 현재, ATL에서 생성 된 서비스를 지원 EXE 당 하나의 서비스 합니다. 따라서 배열에 서비스 이름을 포함 하는 단일 항목이 및 **_ServiceMain** 시작 함수로 합니다. **_ServiceMain** 의 정적 멤버 함수는 `CAtlServiceModuleT` 비정적 멤버 함수를 호출 하는 `ServiceMain`합니다.  
  
> [!NOTE]
>  오류 **StartServiceCtrlDispatcher** 서비스 제어에 연결할 관리자 (SCM) 아마 서비스에 프로그램이 실행 중인지 합니다. 이 경우 프로그램 호출 `CAtlServiceModuleT::Run` 직접 프로그램을 로컬 서버로 실행할 수 있도록 합니다. 로컬 서버로 프로그램을 실행 하는 방법에 대 한 자세한 내용은 참조 [디버그 팁](../atl/debugging-tips.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

