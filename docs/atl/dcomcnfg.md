---
title: DCOMCNFG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DCOMCNFG
dev_langs:
- C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a165102294f9f39d25f0c3118251382ecab067b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="dcomcnfg"></a>DCOMCNFG
**DCOMCNFG** 는 레지스트리에서 다양 한 DCOM 관련 설정을 구성할 수 있도록 하는 Windows NT 4.0 유틸리티입니다. **DCOMCNFG** 창에 있는 3 개의 페이지가: 기본 보안, 기본 속성 및 응용 프로그램입니다. Windows 2000에서 네 번째 페이지에서 기본 프로토콜은 존재 합니다.  
  
## <a name="default-security-page"></a>기본 보안 페이지  
 시스템 개체에 대 한 기본 사용 권한을 지정 하는 기본 보안 페이지를 사용할 수 있습니다. 기본 보안 페이지에 세 개의 섹션이: 액세스, 시작 및 구성 합니다. 섹션의 기본값을 변경 하려면 해당 클릭 **기본값 편집** 단추입니다. 이러한 기본 보안 설정은 레지스트리에 저장 됩니다 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`합니다.  
  
## <a name="default-protocols-page"></a>기본 프로토콜 페이지  
 이 페이지는이 컴퓨터에서 DCOM을 사용할 수 있는 네트워크 프로토콜의 집합을 나열합니다. 순서 있는 사용 될; 우선 순위를 반영 합니다. 목록에서 첫 번째 가장 높은 우선 순위를 갖습니다. 프로토콜을 추가 하거나이 페이지에서 삭제 될 수 있습니다.  
  
## <a name="default-properties-page"></a>기본 속성 페이지  
 기본 속성 페이지에서 선택 해야는 **이 컴퓨터에서 DCOM 사용** 확인란이이 컴퓨터에서 실행 되는 액세스 COM 개체에 다른 컴퓨터에 클라이언트를 선택 합니다. 이 옵션을 선택 하 고 `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` 값을 `Y`합니다.  
  
## <a name="applications-page"></a>응용 프로그램 페이지  
 응용 프로그램 페이지와 특정 개체에 대 한 설정을 변경할 수 있습니다. 단순히 목록에서 응용 프로그램을 선택 하 고 클릭는 **속성** 단추입니다. 속성 창에 5 개 페이지가 있습니다.  
  
-   일반 페이지 사용 하는 응용 프로그램을 확인 합니다.  
  
-   위치 페이지를 사용 하면 클라이언트가 호출할 때 응용 프로그램 실행 위치를 지정할 수 있습니다 `CoCreateInstance` 관련 CLSID에 있습니다. 선택 하는 경우는 **다음 컴퓨터에서 응용 프로그램을 실행** 확인란을 선택 하 고 컴퓨터 이름을 입력 한 다음 `RemoteServerName` appid에 해당 응용 프로그램에 대 한 값이 추가 됩니다. 지우기는 **이 컴퓨터에 응용 프로그램을 실행** 확인란 이름 바꾸기는 `LocalService` 값을 `_LocalService` 및를 사용 하지 않도록 설정 합니다.  
  
-   기본 보안에서 페이지를 찾을 수 있는 보안 페이지 비슷합니다는 **DCOMCNFG** 창 제외 하 고 현재 응용 프로그램에만 이러한 설정을 적용 합니다. 다시, appid에 해당 개체에 대 한 설정이 저장 됩니다.  
  
-   식별 페이지 식별 어떤 사용자는 응용 프로그램을 실행 하는 데 사용 됩니다.  
  
-   끝점 페이지 프로토콜 및 선택한 서버의 DCOM 클라이언트에서 사용할 수 있는 끝점의 집합을 나열합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)

