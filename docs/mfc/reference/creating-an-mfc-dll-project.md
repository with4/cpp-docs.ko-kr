---
title: "MFC DLL 프로젝트 만들기 | Microsoft Docs"
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
  - "vc.appwiz.mfcdll.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 만들기"
  - "DLL[C++], MFC"
  - "MFC DLL[C++], 프로젝트 만들기"
  - "프로젝트[C++], 만들기"
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC DLL 프로젝트 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL은 여러 응용 프로그램에서 동시에 사용할 수 있는 함수의 공유 라이브러리 역할을 하는 이진 파일입니다.  MFC DLL 프로젝트를 만드는 가장 쉬운 방법은 MFC DLL 마법사를 사용하는 것입니다.  
  
> [!NOTE]
>  실제 설정이나 버전에 따라서 IDE에 나타나는 기능의 모양이 도움말의 설명과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### MFC DLL 마법사를 사용하여 MFC DLL 프로젝트를 만들려면  
  
1.  [Visual C\+\+ 응용 프로그램 마법사로 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md) 도움말 항목에 설명되어 있는 지침을 따릅니다.  
  
 **참고 새 프로젝트** 대화 상자의 템플릿 창에서 `MFC DLL` 아이콘을 선택하여 MFC DLL 마법사를 엽니다.  
  
1.  [MFC DLL 마법사](../../mfc/reference/mfc-dll-wizard.md)의 [응용 프로그램 설정](../../mfc/reference/application-settings-mfc-dll-wizard.md) 페이지를 사용하여 응용 프로그램 설정을 정의합니다.  
  
    > [!NOTE]
    >  마법사의 기본 설정을 그대로 유지하려면 이 단계를 건너 뜁니다.  
  
2.  **마침**을 클릭하여 마법사를 닫고 **솔루션 탐색기**에서 새 프로젝트를 엽니다.  
  
 프로젝트를 만든 후 만들어진 파일을 솔루션 탐색기에서 볼 수 있습니다.  마법사에서 프로젝트용으로 만드는 파일에 대한 자세한 내용은 프로젝트 생성 파일인 ReadMe.txt를 참조하십시오.  파일 형식에 대한 자세한 내용은 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트 형식](../Topic/Debugging%20Preparation:%20Visual%20C++%20Project%20Types.md)   
 [코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/ko-kr/4ff8881d-0daf-47e7-bfe7-774c625031b4)