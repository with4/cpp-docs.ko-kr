---
title: "MFC ActiveX 컨트롤 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], MFC"
  - "MFC ActiveX 컨트롤 마법사"
  - "MFC ActiveX 컨트롤[C++], 마법사"
  - "OLE 컨트롤[C++]"
  - "OLE 컨트롤[C++], 만들기"
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤은 [자동화 서버](../../mfc/automation-servers.md)의 한 종류로, 다시 사용할 수 있는 구성 요소입니다.  ActiveX 컨트롤을 호스팅하는 응용 프로그램은 해당 컨트롤의 [자동화 클라이언트](../../mfc/automation-clients.md)입니다.  다시 사용할 수 있는 구성 요소를 만드는 것이 목적인 경우에는 이 마법사를 사용하여 컨트롤을 만드십시오.  자세한 내용은 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)을 참조하십시오.  
  
 또한 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)를 사용하여 자동화 서버 MFC 응용 프로그램을 만들 수 있습니다.  
  
 이 마법사를 사용하여 만든 ActiveX 컨트롤은 사용자 인터페이스를 가질 수도 있고, 보이지 않도록 만들 수도 있습니다.  마법사의 [컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지에서 이 옵션을 설정할 수 있습니다.  타이머 컨트롤은 보이지 않도록 설정할 수 있는 ActiveX 컨트롤의 한 예입니다.  
  
 ActiveX 컨트롤은 복잡한 사용자 인터페이스를 가질 수 있습니다.  일부 컨트롤은 캡슐화된 폼과 같은 형태일 수 있습니다. 즉, 하나의 컨트롤에 여러 필드가 들어 있으며 각 필드는 고유한 Windows 컨트롤입니다.  예를 들어, MFC ActiveX 컨트롤로 구현된 자동차 부품 개체는 사용자가 부품 번호, 부품 이름 및 기타 정보를 읽고 편집할 수 있는 폼 형태의 사용자 인터페이스를 가질 수 있습니다.  자세한 내용은 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)을 참조하십시오.  
  
 ActiveX 개체의 컨테이너를 만들려는 경우에는 [ActiveX 컨트롤 컨테이너 만들기](../../mfc/reference/creating-an-mfc-activex-control-container.md)를 참조하십시오.  
  
 MFC 기초 프로그램에는 C\+\+ 소스 파일\(.cpp\), 리소스 파일\(.rc\) 및 프로젝트 파일\(.vcxproj\)이 포함됩니다.  이 기초 파일에서 생성된 코드는 MFC를 기반으로 합니다.  
  
 다음 샘플 목록은 ActiveX 컨트롤에 대한 작업 및 성능 향상을 위한 여러 가지 방법입니다.  
  
-   [ActiveX 컨트롤 최적화](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [ActiveX 컨트롤에 스톡 이벤트 추가](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [사용자 지정 이벤트 추가](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [스톡 메서드 추가](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [사용자 지정 메서드 추가](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [스톡 속성 추가](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [사용자 지정 속성 추가](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## 개요  
 이 마법사 페이지에서는 만들고 있는 MFC ActiveX 컨트롤 프로젝트의 현재 응용 프로그램 설정을 설명합니다.  마법사에서 프로젝트를 만들 때 사용하는 기본 설정은 다음과 같습니다.  
  
-   기본 프로젝트는 런타임 라이선스나 도움말 파일을 생성하지 않습니다.  이러한 기본 설정은 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) 페이지에서 변경할 수 있습니다.  ActiveX 컨트롤 마법사의 이 페이지에서 선택한 내용만 **개요** 페이지에 반영됩니다.  
  
-   프로젝트에는 프로젝트 이름을 기반으로 하는 컨트롤 클래스 및 속성 페이지 클래스가 포함됩니다.  [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md) 페이지에서 프로젝트 및 파일 이름을 편집할 수 있습니다.  
  
-   컨트롤은 기존 Windows 컨트롤을 기반으로 하지 않으며, 표시되었을 때 활성화되고, 사용자 인터페이스를 가지며, **정보** 대화 상자를 포함합니다.  [컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지에서 이러한 기본 설정을 변경할 수 있습니다.  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트 만들기 및 관리](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C\+\+ 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [개념](../../atl/active-template-library-atl-concepts.md)