---
title: 로컬 서버로 프로그램을 실행 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2b8a79978528493e02ac5a272dafe8da6fdc1d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="running-the-program-as-a-local-server"></a>로컬 서버로 프로그램을 실행합니다.
프로그램을 서비스로 실행를 편리 하 게 없는 경우 프로그램이 정상 로컬 서버로 실행 될 수 있도록 레지스트리를 일시적으로 변경할 수 있습니다. 단순히 이름 바꾸기는 `LocalService` 프로그램 AppID 아래의 값 `_LocalService` 확인는 `LocalServer32` 프로그램 CLSID 아래 키가 올바르게 설정 합니다. (참고는 DCOMCNFG를 사용 하 여 다른 컴퓨터에 응용 프로그램을 실행 해야 함을 지정 하려면 이름을 변경 하면 `LocalServer32` 키를 `_LocalServer32`.) 때문에 로컬 서버 시작 시에 몇 초를 사용 하면 프로그램 실행에 대 한 호출 **StartServiceCtrlDispatcher** 에 `CAtlServiceModuleT::Start` 실패 하기 전에 몇 초입니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 팁](../atl/debugging-tips.md)

