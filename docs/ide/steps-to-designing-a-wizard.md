---
title: "마법사 디자인 단계 | Microsoft Docs"
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
  - "사용자 지정 마법사, 디자인"
ms.assetid: dc22746b-99e3-4569-a8b4-b3d7cbabf8f2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 마법사 디자인 단계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마법사를 사용하면 공용 프로젝트 시작 파일을 만들고 구성할 수 있습니다.  프로젝트를 만들 때처럼 마법사를 만들 때에도 계획을 작성해야 합니다.  다음 단계에서는 Visual C\+\+ 사용자 지정 마법사 사용 방법을 익히고 사용자의 프로젝트에 적용하는 방법을 설명합니다.  
  
1.  Visual Studio에 포함된 [사용자 지정 마법사 샘플](http://msdn.microsoft.com/ko-kr/6afa2143-062c-4a68-81ca-66cbf4b95261)을 확인합니다.  
  
2.  마법사에서 만들 프로젝트 형식에 대한 기본 설정을 지정합니다.  응용 프로그램을 만드는 경우처럼 이 과정에는 서로 다른 많은 반복 작업이 필요합니다.  
  
3.  Visual C\+\+ [사용자 지정 마법사](../ide/creating-a-custom-wizard.md)에서 사용자 인터페이스와 페이지 수 옵션을 지정하여 프로젝트를 만듭니다.  
  
    > [!NOTE]
    >  사용자 인터페이스를 지정하지 않는 경우, 즉 사용자 지정 마법사의 [사용자 지정 마법사, 응용 프로그램 설정](../ide/application-settings-custom-wizard.md)에서 **사용자 인터페이스**의 선택을 취소하는 경우, 마법사에서는 사용자 지정 매개 변수를 WIZARD\_UI\=**FALSE**로 설정하여 사용자 입력과 .htm 파일이 없는 프로젝트 템플릿 파일을 만듭니다.  즉, 페이지 수를 지정하지 않습니다.  자세한 내용은 [.vsz 파일\(프로젝트 컨트롤\)](../ide/dot-vsz-file-project-control.md)을 참조하십시오.  
  
4.  사용자 지정 마법사에서 만드는 [기본 마법사 프로젝트를 검사](../ide/examining-the-basic-wizard-project.md)합니다.  
  
5.  마법사에 사용자 인터페이스가 있으면 마법사를 실행하여 [마법사의 메커니즘에 대한 자세한 내용](../ide/examining-the-mechanics-of-a-wizard.md)을 봅니다.  
  
6.  [기본 마법사를 사용자 지정](../ide/customizing-your-wizard.md)합니다.  
  
7.  [상황에 맞는 도움말을 추가](../ide/providing-context-sensitive-help.md)합니다.  
  
8.  JScript 및 HTML 코드에 대한 [마법사에서 오류 처리](../ide/handling-errors-in-wizards.md)합니다.  
  
9. 마법사를 빌드하고 테스트합니다.  
  
10. 마법사를 디버깅합니다.  자세한 내용은 [스크립트 및 웹 응용 프로그램 디버깅](../Topic/Debugging%20Web%20Applications%20and%20Script.md)을 참조하십시오.  
  
    > [!NOTE]
    >  JScript를 디버깅할 경우 네이티브 코드에서 혼합 모드 디버깅을 수행할 수 없습니다.  
  
## 참고 항목  
 [사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)   
 [사용자 지정 마법사](../ide/custom-wizard.md)   
 [마법사용으로 만들어진 파일](../ide/files-created-for-your-wizard.md)