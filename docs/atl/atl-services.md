---
title: "ATL 서비스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CServiceModule
dev_langs: C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d13eebbe96ba57c82e3bf1c360b0cb471a6bd975
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-services"></a>ATL 서비스
ATL COM 개체를 만들려면 서비스에서 실행 되도록 ATL 프로젝트 마법사에서 서버 옵션의 목록에서 서비스 (EXE)를 선택 합니다. 파생 된 클래스 다음 만들어집니다 `CAtlServiceModuleT` 은 서비스 구현에 있습니다.  
  
 ATL COM 개체를 서비스로 작성 되 면 로컬 서버로 등록 됩니다 및 제어판의 서비스 목록에 나타나지 않습니다. 즉, 서비스로 서 보다 로컬 서버로 서비스를 디버깅 하는 것이 쉽습니다. 서비스로 설치 하려면 명령 프롬프트에서 다음을 실행 합니다.  
  
 `YourEXE` `.exe /Service`  
  
 파일을 제거 하려면 다음을 실행 합니다.  
  
 `YourEXE` `.exe /UnregServer`  
  
 이 섹션의 처음 4 개 항목 실행 하는 동안 발생 하는 작업에 설명 `CAtlServiceModuleT` 멤버 함수입니다. 이러한 항목 이라고 하는 함수는 일반적으로 동일한 순서로 나타납니다. 이러한 항목에 대 한 이해를 향상을 위해 것이 참조로 ATL 프로젝트 마법사에 의해 생성 된 소스 코드를 사용 하는 것이 좋습니다. 이러한 처음 네 개의 주제는 같습니다.  
  

-   [CAtlServiceModuleT::Start 함수](../atl/reference/catlservicemodulet-class.md#start)  
  
-   [CAtlServiceModuleT::ServiceMain 함수](../atl/reference/catlservicemodulet-class.md#servicemain)  
  
-   [CAtlServiceModuleT::Run 함수](../atl/reference/catlservicemodulet-class.md#run)  
  
-   [CAtlServiceModuleT::Handler 함수](../atl/reference/catlservicemodulet-class.md#handler)  
  
 마지막 세 항목 서비스를 개발 하는 데 관련 된 개념에 설명 합니다.  
  
-   [레지스트리 항목](../atl/registry-entries.md) ATL 서비스  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [디버깅 팁](../atl/debugging-tips.md) ATL 서비스  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)

