---
title: "NMake 속성 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.ReBuildCommandLine"
  - "VC.Project.VCNMakeTool.CleanCommandLine"
  - "VC.Project.VCNMakeTool.Output"
  - "VC.Project.VCNMakeTool.BuildCommandLine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMake 속성 페이지"
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# NMake 속성 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**NMake** 속성 페이지를 사용하여 NMake 프로젝트의 빌드 설정을 지정할 수 있습니다.  
  
 NMake 프로젝트에 대한 자세한 내용은 [메이크파일 프로젝트 만들기](../ide/creating-a-makefile-project.md)를 참조하십시오.  
  
 **NMake** 속성 페이지에는 다음 속성이 포함되어 있습니다.  
  
## UI 요소 목록  
 **빌드 명령줄**  
 **빌드** 메뉴에서 **빌드**를 클릭한 경우 실행될 명령을 지정합니다.  
  
 **모두 다시 빌드 명령줄**  
 **빌드** 메뉴에서 **모두 다시 빌드**를 클릭한 경우 실행될 명령을 지정합니다.  
  
 **정리 명령줄**  
 **빌드** 메뉴에서 **정리**를 클릭한 경우 실행될 명령을 지정합니다.  
  
 **Output**  
 명령줄의 출력을 포함하는 파일 이름을 지정합니다.  기본적으로 이 파일 이름은 프로젝트 이름을 기본으로 합니다.  
  
 **전처리기 정의**  
 소스 파일에서 사용하는 전처리기 정의를 지정합니다.  기본값은 현재 플랫폼 및 구성에 의해 결정됩니다.  
  
 **포함 검색 경로**  
 컴파일러가 포함 파일을 검색할 디렉터리를 지정합니다.  
  
 **Forced Includes**  
 프로젝트 파일에 포함되지 않은 경우에도 자동으로 전처리기가 처리하는 파일을 지정합니다.  
  
 **어셈블리 검색 경로**  
 .NET 어셈블리를 확인하려고 할 때 .NET Framework가 검색할 디렉터리를 지정합니다.  
  
 **어셈블리 강제 사용**  
 .NET Framework가 자동으로 처리하는 어셈블리를 지정합니다.  
  
 **추가 옵션**  
 모든 C\+\+ 파일을 구문 분석할 때 사용할 IntelliSense에 대한 추가 컴파일러 스위치를 지정합니다.  
  
 **NMake** 속성 페이지에 액세스하는 방법에 대한 정보는 [방법: 속성 페이지로 프로젝트 속성 지정](../misc/how-to-specify-project-properties-with-property-pages.md)를 참조하십시오.  
  
 이 개체의 멤버에 프로그래밍 방식으로 액세스하는 방법에 대한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>을 참조하십시오.  
  
## 참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [방법: 메이크파일 프로젝트에 IntelliSense 사용](../ide/how-to-enable-intellisense-for-makefile-projects.md)