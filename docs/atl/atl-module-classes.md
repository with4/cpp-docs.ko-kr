---
title: "ATL 모듈 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 모듈 클래스"
  - "CComModule 클래스, 변경 사항"
  - "모듈 클래스"
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 모듈 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모듈 클래스는 ATL 7.0의 새로운이 항목을 설명 합니다.  
  
## CComModule 대체 클래스  
 이전 버전의 ATL 사용 `CComModule`.  ATL 7.0에서 `CComModule` 기능 몇 가지 클래스에 의해 대체 됩니다.  
  
-   [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL.를 사용 하는 대부분의 응용 프로그램에서 필요한 정보를 포함 합니다.  HINSTANCE 리소스 인스턴스 및 모듈을 포함합니다.  
  
-   [CAtlComModule](../atl/reference/catlcommodule-class.md) atl에서 COM 클래스에서 필요한 정보를 포함 합니다.  
  
-   [CAtlWinModule](../atl/reference/catlwinmodule-class.md) 는 atl에서 창 클래스에서 필요한 정보를 포함 합니다.  
  
-   [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) 디버깅 인터페이스에 대 한 지원을 포함 합니다.  
  
-   [CAtlModule](../atl/reference/catlmodule-class.md) 다음 `CAtlModule`\-파생된 클래스는 특정 응용 프로그램 종류에 필요한 정보를 포함 하는 사용자 지정 합니다.  이러한 클래스의 대부분의 멤버는 재정의할 수 있습니다.  
  
    -   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL 응용 프로그램에서 사용 합니다.  표준 내보내기에 대 한 코드를 제공합니다.  
  
    -   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE 응용 프로그램에 사용 합니다.  EXE에서 필요로 하는 코드를 제공 합니다.  
  
    -   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT 및 Windows 2000 서비스를 만들기 위한 지원을 제공 합니다.  
  
 `CComModule`이전 버전과 호환성을 위해 여전히 사용할 수 있습니다.  
  
## CComModule 기능을 배포 하는 이유  
 기능을 `CComModule` 몇 가지 새 클래스에는 다음과 같은 이유로 배포 된.  
  
-   기능에 게 `CComModule` 세밀 하 게 합니다.  
  
     COM, 창 작업, 인터페이스 디버깅 및 응용 프로그램별 \(DLL 또는 EXE\) 기능에 대 한 지원은 이제 별도 클래스에 있습니다.  
  
-   이러한 각 모듈의 전역 인스턴스를 자동으로 선언 합니다.  
  
     필수 모듈 클래스의 전역 인스턴스를 프로젝트에 연결 되어 있습니다.  
  
-   용어 및 Init 메서드 호출의 필요성을 제거 합니다.  
  
     용어 및 Init 메서드 모듈 클래스의 생성자와 소멸자에 옮겼습니다. 더 이상 Init 및 용어를 호출할 필요가 없습니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [Class Overview](../atl/atl-class-overview.md)