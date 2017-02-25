---
title: "메이크파일 프로젝트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.makefile.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메이크파일 프로젝트, 만들기"
  - "프로젝트 파일[C++], 메이크파일 프로젝트"
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 메이크파일 프로젝트 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메이크파일을 사용하여 명령줄에서 프로젝트를 빌드하면 Visual Studio 개발 환경에서 프로젝트를 인식하지 못합니다.  [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], [!INCLUDE[vsPro](../ide/includes/vspro_md.md)] 또는 Visual Studio Express for Windows Desktop을 사용하여 프로젝트를 열고 빌드하려면 먼저 MakeFile 프로젝트 템플릿을 선택하여 빈 프로젝트를 만듭니다.  그런 다음 이 프로젝트를 사용하여 Visual Studio 개발 환경에서 프로젝트를 빌드할 수 있습니다.  
  
 프로젝트는 솔루션 탐색기에 파일을 표시하지 않습니다.  프로젝트에서는 빌드 설정을 지정하고, 설정 내용은 프로젝트의 속성 페이지에 반영됩니다.  
  
 프로젝트에서 지정하는 출력 파일은 빌드 스크립트가 생성하는 이름에는 영향을 미치지 않으며 의도만 선언합니다.  
  
### 메이크파일 프로젝트를 만들려면  
  
1.  [Visual C\+\+ 응용 프로그램 마법사로 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md) 도움말 항목에 설명되어 있는 지침을 따릅니다.  
  
2.  **새 프로젝트** 대화 상자의 템플릿 창에서 **메이크파일 프로젝트**를 선택하여 마법사를 엽니다.  
  
3.  [응용 프로그램 설정](../ide/application-settings-makefile-project-wizard.md) 페이지에서 명령, 출력, 정리 및 다시 빌드 정보를 입력합니다.  
  
4.  **마침**을 클릭하여 마법사를 닫고 **솔루션 탐색기**에서 새로 만든 프로젝트를 엽니다.  
  
 속성 페이지에서 프로젝트의 속성을 보고 편집할 수 있습니다.  속성 페이지 표시에 대한 자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../ide/working-with-project-properties.md)을 참조하십시오.  
  
## 참고 항목  
 [메이크파일 프로젝트 마법사](../ide/makefile-project-wizard.md)   
 [메이크파일의 특수 문자](../build/special-characters-in-a-makefile.md)   
 [메이크파일의 내용](../build/contents-of-a-makefile.md)