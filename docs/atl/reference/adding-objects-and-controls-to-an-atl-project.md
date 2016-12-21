---
title: "ATL 프로젝트에 개체 및 컨트롤 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 컨트롤 마법사"
  - "ATL 프로젝트, 컨트롤 추가"
  - "ATL 프로젝트, 개체 추가"
  - "컨트롤[ATL], 프로젝트에 추가"
  - "개체[C++], ATL 프로젝트에 추가"
  - "마법사[C++], ATL 프로젝트"
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 프로젝트에 개체 및 컨트롤 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 코드 마법사 중 하나를 사용하여 ATL 또는 MFC 기반 프로젝트에 개체 또는 컨트롤을 추가할 수 있습니다.  추가하는 각 COM 개체 또는 컨트롤에 대해 스크립트 기반 레지스트리 지원을 위한 .rgs 파일뿐만 아니라 .cpp 및 .h 파일도 생성됩니다.  Visual Studio에서 사용할 수 있는 ATL 코드 마법사는 다음과 같습니다.  
  
||||  
|-|-|-|  
|[ATL 단순 개체](../../atl/reference/atl-simple-object-wizard.md)|[ATL 대화 상자](../../atl/reference/atl-dialog-wizard.md)|[ATL 컨트롤](../../atl/reference/atl-control-wizard.md)|  
|[ATL 속성 페이지](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page 구성 요소](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLE DB 소비자](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[MFC에 ATL 지원 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM\+ 1.0 구성 요소 마법사](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB 공급자](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  프로젝트에 ATL 개체를 추가하려면 먼저 관련 도움말 항목에서 개체에 대한 세부 정보와 요구 사항을 검토해야 합니다.  
  
### ATL 컨트롤 마법사를 사용하여 개체 또는 컨트롤을 추가하려면  
  
1.  솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **추가**를 클릭합니다.  **클래스 추가**를 클릭합니다.  
  
     [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자가 나타납니다.  
  
2.  범주 창에서 ATL 폴더를 선택하고 템플릿 창에서 삽입할 개체를 선택합니다.  **열기**를 클릭합니다.  선택한 개체에 대한 코드 마법사가 나타납니다.  
  
    > [!NOTE]
    >  ATL 개체를 MFC 프로젝트에 추가하려면 먼저 기존 프로젝트에 ATL 지원을 추가해야 합니다.  [MFC 프로젝트에 ATL 지원 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) 항목에 설명되어 있는 지침을 따라 기존 프로젝트에 ATL 지원을 추가할 수 있습니다.  
  
     또한 ATL 지원을 미리 추가하지 않고 MFC 프로젝트에 ATL 개체를 추가하려고 하면 프로젝트에 ATL 지원을 추가할지 지정하라는 메시지가 나타납니다.  **예**를 클릭하여 ATL 지원을 프로젝트에 추가하고 선택된 ATL 마법사를 엽니다.  
  
## 참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual C\+\+ 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)