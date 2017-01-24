---
title: "MFC ActiveX 컨트롤 만들기 | Microsoft Docs"
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
  - "vc.appwiz.activex.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 만들기"
  - "MFC ActiveX 컨트롤[C++], 만들기"
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤 프로그램은 상위 응용 프로그램에 특정 유형의 기능을 제공하도록 설계된 모듈식 프로그램입니다.  예를 들어, 대화 상자에서 사용할 단추나 웹 페이지에서 사용할 도구 모음과 같은 컨트롤을 만들 수 있습니다.  
  
 MFC ActiveX 컨트롤을 만드는 가장 쉬운 방법은 [MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)를 사용하는 것입니다.  
  
### MFC ActiveX 컨트롤 마법사를 사용하여 MFC ActiveX 컨트롤을 만들려면  
  
1.  [Visual C\+\+ 응용 프로그램 마법사로 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md) 도움말 항목에 설명되어 있는 지침을 따릅니다.  
  
2.  **새 프로젝트** 대화 상자에서 템플릿 창의 **MFC ActiveX 컨트롤** 아이콘을 선택하여 MFC ActiveX 컨트롤 마법사를 엽니다.  
  
3.  MFC ActiveX 컨트롤 마법사를 사용하여 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [컨트롤 이름](../../mfc/reference/control-names-mfc-activex-control-wizard.md) 및 [컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)을 정의합니다.  
  
    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.  
  
4.  **마침**을 클릭하여 마법사를 닫고 새 프로젝트를 개발 환경에서 엽니다.  
  
 프로젝트를 만든 후 만들어진 파일을 **솔루션 탐색기**에서 볼 수 있습니다.  마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하십시오.  파일 형식에 대한 자세한 내용은 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)을 참조하십시오.  
  
 프로젝트를 만든 후 코드 마법사를 사용하여 [함수](../../ide/add-member-function-wizard.md), [변수](../../ide/add-member-variable-wizard.md), [이벤트](../../ide/add-event-wizard.md), [속성](../../ide/names-add-property-wizard.md) 및 [메서드](../../ide/add-method-wizard.md)를 추가할 수 있습니다.  ActiveX 컨트롤 사용자 지정에 대한 자세한 내용은[MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)을 참조하십시오.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ko-kr/4ff8881d-0daf-47e7-bfe7-774c625031b4)