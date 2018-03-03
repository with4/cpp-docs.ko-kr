---
title: "MFC ActiveX 컨트롤 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82e562ceb73da2b103360ab9607cecbbe9f1da02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사
ActiveX 컨트롤은 특정 유형의 [자동화 서버](../../mfc/automation-servers.md);는 재사용 가능한 구성 요소입니다. ActiveX 컨트롤을 호스팅하는 응용 프로그램은는 [자동화 클라이언트](../../mfc/automation-clients.md) 해당 컨트롤의 합니다. 이러한 다시 사용할 수 있는 구성 요소를 만드는 것이 목표인 경우 컨트롤을 만드는이 마법사를 사용 합니다. 참조 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md) 자세한 정보에 대 한 합니다.  
  
 자동화 서버 MFC를 통해 응용 프로그램을 만들 수 또는 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)합니다.  
  
 이 마법사를 사용 하 여 만든 ActiveX 컨트롤을 사용자 인터페이스를 사용할 수 있습니다 또는 표시 되지 않을 수도 있습니다. 이 옵션을 설정할 수는 [제어 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 마법사의 페이지입니다. 타이머 컨트롤은 표시 되지 않도록 하려면 원하는 ActiveX 컨트롤의 예입니다.  
  
 ActiveX 컨트롤은 복잡 한 사용자 인터페이스를 사용할 수 있습니다. 캡슐화 된 폼과 같은 일부 컨트롤 수: 많은 포함 하는 한 컨트롤 필드를 각각 그 자체로 Windows 컨트롤입니다. 예를 들어, MFC ActiveX 컨트롤 같은 구현 자동차 부품 개체는 폼과 비슷한 사용자 인터페이스는 사용자 수 읽기 및 편집 부품 번호, 파트 이름 및 기타 정보를 발생할 수 있습니다. 참조 [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md) 자세한 정보에 대 한 합니다.  
  
 ActiveX 개체에 대 한 컨테이너를 만들어야 할 경우 참조 [ActiveX 컨트롤 컨테이너 만들기](../../mfc/reference/creating-an-mfc-activex-control-container.md)합니다.  
  
 C + + 소스 (.cpp) 파일, 리소스 (.rc) 파일 및 프로젝트 (.vcxproj) 파일을 포함 하는 MFC 시작 프로그램입니다. 이 기초 파일에서 생성 된 코드는 MFC를 기반으로 합니다.  
  
 다음 샘플은 작업 및 성능 ActiveX 컨트롤에 대 한 향상 된 기능을 보여 줍니다.  
  
-   [ActiveX 컨트롤 최적화](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [ActiveX 컨트롤에 스톡 이벤트 추가](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [사용자 지정 이벤트 추가](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [스톡 메서드 추가](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [사용자 지정 메서드 추가](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [스톡 속성 추가](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [사용자 지정 속성 추가](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤 프로그래밍](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## <a name="overview"></a>개요  
 이 마법사 페이지에서는 만들려는 MFC ActiveX 컨트롤 프로젝트에 대 한 현재 응용 프로그램 설정을 설명 합니다. 기본적으로 마법사에서 다음과 같이 프로젝트를 만들어집니다.  
  
-   기본 프로젝트에는 없는 런타임 라이선스 또는 도움말 파일을 생성합니다. 이러한 기본 설정을 변경할 수 있습니다는 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) 페이지. ActiveX 컨트롤 마법사의이 페이지에서 선택한만에 반영 됩니다는 **개요** 페이지.  
  
-   컨트롤 클래스 및 프로젝트의 이름을 기반으로 하는 속성 페이지 클래스 프로젝트에 포함 되어 있습니다. 프로젝트 및 파일 이름을 편집할 수는 [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md) 페이지.  
  
-   컨트롤 없는 기존 Windows 컨트롤에 따라, 표시 되 고 사용자 인터페이스가, 포함 하는 경우 활성화 되는 **에 대 한** 대화 상자. 이러한 기본 설정을 변경할 수 있습니다는 [제어 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트 만들기 및 관리](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [개념](../../atl/active-template-library-atl-concepts.md)

