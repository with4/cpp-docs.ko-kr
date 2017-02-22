---
title: "ATL 프로젝트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MIN_CRT 매크로"
  - "ATL 프로젝트, 만들기"
  - "ATL70.DLL"
  - "ATL 구성 요소를 사용하여 파일 배포"
ms.assetid: 061d5f98-f669-440e-9380-42f017a0f9e8
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL 프로젝트 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가장 쉽게 ATL 프로젝트를 만드는 방법은 **새 프로젝트** 대화 상자의 Win32 프로젝트 폴더에 있는 ATL 프로젝트 마법사를 사용하는 것입니다.  
  
### ATL 프로젝트 마법사를 사용하여 ATL 프로젝트를 만들려면  
  
1.  [Visual C\+\+ 응용 프로그램 마법사로 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md) 항목에 설명되어 있는 지침을 따릅니다.  
  
2.  템플릿 창에서 **ATL 프로젝트** 아이콘을 선택하여 ATL 프로젝트 마법사를 엽니다.  
  
3.  `ATL Project Wizard`의 [응용 프로그램 설정](../../atl/reference/application-settings-atl-project-wizard.md) 페이지를 사용하여 응용 프로그램 설정을 정의합니다.  
  
    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.  
  
4.  **마침**을 클릭하여 마법사를 닫고 새 프로젝트를 개발 환경에서 엽니다.  
  
 프로젝트를 만든 후 **솔루션 탐색기**에서 프로젝트 관련 파일을 볼 수 있습니다.  마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하십시오.  파일 형식에 대한 자세한 내용은 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)을 참조하십시오.  새 ATL 프로젝트의 구성과 구성 변경 방법에 대한 자세한 내용은 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)을 참조하십시오.  
  
## 참고 항목  
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ko-kr/4ff8881d-0daf-47e7-bfe7-774c625031b4)