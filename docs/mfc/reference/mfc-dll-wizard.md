---
title: "MFC DLL 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.dll.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL 마법사[MFC]"
  - "DLL[C++], 만들기"
  - "DLL[C++], MFC"
  - "MFC DLL 마법사"
  - "MFC DLL[C++]"
  - "MFC DLL[C++], 만들기"
ms.assetid: 4e936031-7e39-4f40-a295-42a09c5ff264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC DLL 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL 마법사를 사용하여 MFC DLL 프로젝트를 만드는 경우 기본 제공된 기능이 있는 기초 응용 프로그램을 사용하게 됩니다. 이 기초 응용 프로그램은 컴파일될 경우 [DLL](../../build/dlls-in-visual-cpp.md)의 기본 기능을 구현합니다.  MFC 기초 프로그램에는 C\+\+ 소스 파일\(.cpp\), 리소스 파일\(.rc\) 및 프로젝트 파일\(.vcxproj\)이 포함됩니다.  이 기초 파일에서 생성된 코드는 MFC를 기반으로 합니다.  자세한 내용은 Visual Studio에서 프로젝트용으로 생성되는 Readme.txt 파일의 내용과 [MFC DLL 마법사에 의해 생성된 클래스 및 함수](../../mfc/reference/classes-and-functions-generated-by-the-mfc-dll-wizard.md)를 참조하십시오.  
  
## 개요  
 이 마법사 페이지에서는 현재 만들고 있는 [MFC DLL 프로젝트의 응용 프로그램 설정](../../mfc/reference/application-settings-mfc-dll-wizard.md)을 설명합니다.  기본적으로 프로젝트는 추가 설정 없이 기본 DLL\(MFC 공유\) 프로젝트로 만들어집니다.  
  
 기본값을 변경하려면 마법사의 왼쪽 열에 있는 **응용 프로그램 설정**을 클릭하고 MFC DLL 마법사의 해당 페이지에서 필요한 사항을 변경합니다.  
  
 MFC DLL 프로젝트를 만든 후 Visual C\+\+ [코드 마법사](../../ide/adding-functionality-with-code-wizards-cpp.md)를 사용하여 프로젝트에 개체 또는 컨트롤을 추가할 수 있습니다.  
  
 기본 MFC DLL 프로젝트에 대해 수행할 수 있는 작업 및 성능 향상을 위한 방법에는 다음과 같은 것들이 있습니다.  
  
-   [DLL에서 내보내기](../../build/exporting-from-a-dll.md)  
  
-   [DLL에 실행 파일 링크](../../build/linking-an-executable-to-a-dll.md)  
  
-   [DLL 초기화](../../build/initializing-a-dll.md)  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트 만들기 및 관리](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/ko-kr/4ff8881d-0daf-47e7-bfe7-774c625031b4)   
 [MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)   
 [멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)   
 [인터페이스 구현](../../ide/implementing-an-interface-visual-cpp.md)   
 [다른 언어에 대한 마법사 지원](../../ide/wizard-support-for-other-languages.md)