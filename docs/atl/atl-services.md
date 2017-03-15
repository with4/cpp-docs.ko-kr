---
title: "ATL 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 서비스"
  - "COM 개체, ATL"
  - "CServiceModule 클래스"
  - "서비스, ATL"
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL 서비스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램이 서비스에서 실행 되도록 ATL COM 개체를 만들려면 서비스 \(EXE\)의 ATL 프로젝트 마법사에서 서버 옵션 목록에서 선택 하기만 하면 됩니다.  마법사에서 파생 된 클래스를 만듭니다 다음 `CAtlServiceModuleT` 서비스를 구현 합니다.  
  
 ATL COM 개체를 서비스로 빌드되면 로컬 서버로 등록 및 제어판의 서비스 목록에 표시 됩니다.  이 서비스 보다 로컬 서버로 서비스를 디버깅 하는 것이 더 쉽기 때문입니다.  서비스를 설치 하려면 명령 프롬프트에서 다음을 실행 합니다.  
  
 `YourEXE` `.exe /Service`  
  
 제거 하려면 다음을 실행 합니다.  
  
 `YourEXE` `.exe /UnregServer`  
  
 이 단원의 처음 네 실행 하는 동안 발생 하는 작업에 설명 `CAtlServiceModuleT` 멤버 함수입니다.  함수는 일반적으로 호출 되는 이러한 주제와 같은 순서로 나타납니다.  이러한 항목에 대 한 이해를 개선 하 여 ATL 프로젝트 마법사에 대 한 참조를 생성 한 소스 코드를 사용 하는 것이 좋습니다입니다.  처음 네 개의 항목은 다음과 같습니다.  
  
-   [CAtlServiceModuleT::Start 함수](../atl/catlservicemodulet-start-function.md)  
  
-   [CAtlServiceModuleT::ServiceMain 함수](../atl/catlservicemodulet-servicemain-function.md)  
  
-   [CAtlServiceModuleT::Run 함수](../atl/catlservicemodulet-run-function.md)  
  
-   [CAtlServiceModuleT::Handler 함수](../atl/catlservicemodulet-handler-function.md)  
  
 마지막 세 항목 서비스 개발과 관련 된 개념에 설명 합니다.  
  
-   [레지스트리 항목](../atl/registry-entries.md) ATL 서비스에 대 한  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [팁 디버깅](../atl/debugging-tips.md) ATL 서비스에 대 한  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)