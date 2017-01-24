---
title: "MFC 응용 프로그램 마법사 | Microsoft Docs"
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
  - "vc.appwiz.mfc.exe.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "실행 파일, 만들기"
  - "MFC 응용 프로그램 마법사"
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 응용 프로그램 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 응용 프로그램 마법사에서는 컴파일될 경우 Windows 실행 파일\(.exe\) 응용 프로그램의 기본 기능을 구현하는 응용 프로그램을 생성합니다.  MFC 기초 응용 프로그램에는 C\+\+ 소스\(.cpp\) 파일, 리소스\(.rc\) 파일, 헤더\(.h\) 파일 및 프로젝트\(.vcxproj\) 파일이 포함됩니다.  이 기초 파일에서 생성된 코드는 MFC를 기반으로 합니다.  
  
> [!NOTE]
>  선택하는 옵션에 따라 마법사에서는 프로젝트에 추가 파일을 만듭니다.  예를 들어, 마법사의 [고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md) 페이지에서 **상황에 맞는 도움말**을 선택하면 프로젝트의 도움말 파일을 컴파일하는 데 필요한 파일이 만들어집니다.  마법사에서 만드는 파일에 대한 자세한 내용은 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../../ide/file-types-created-for-visual-cpp-projects.md) 및 프로젝트의 Readme.txt 파일을 참조하십시오.  
  
## 개요  
 이 마법사 페이지에서는 만들고 있는 MFC 응용 프로그램에 대한 현재 응용 프로그램 설정을 설명합니다.  마법사에서 프로젝트를 만들 때 사용하는 기본 설정은 다음과 같습니다.  
  
-   [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   프로젝트는 탭 MDI\(다중 문서 인터페이스\) 지원을 포함하도록 만들어집니다.  자세한 내용은 [SDI 및 MDI](../../mfc/sdi-and-mdi.md)을 참조하십시오.  
  
    -   프로젝트는 [문서\/뷰 아키텍처](../../mfc/document-view-architecture.md)를 사용합니다.  
  
    -   프로젝트는 유니코드 라이브러리를 사용합니다.  
  
    -   프로젝트는 Visual Studio 프로젝트 스타일을 사용하여 만들어지며 시각적 스타일 전환이 가능합니다.  
  
    -   프로젝트는 공유 DLL에서 MFC를 사용합니다.  자세한 내용은 [Visual C\+\+의 DLL](../../build/dlls-in-visual-cpp.md)을 참조하십시오.  
  
-   [MFC 응용 프로그램 마법사, 복합 문서 지원](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   프로젝트는 복합 문서를 지원하지 않습니다.  
  
-   [MFC 응용 프로그램 마법사, 문서 템플릿 문자열](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   프로젝트는 기본 문서 템플릿 문자열에 프로젝트 이름을 사용합니다.  
  
-   [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   프로젝트는 데이터베이스를 지원하지 않습니다.  
  
-   [MFC 응용 프로그램 마법사, 사용자 인터페이스 기능](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   프로젝트는 시스템 메뉴, 상태 표시줄, 최대화 및 최소화 상자, **정보** 상자, 표준 메뉴 모음 및 도킹 도구 모음, 자식 프레임 등의 Windows 표준 사용자 인터페이스 기능을 구현합니다.  
  
-   [MFC 응용 프로그램 마법사, 고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   프로젝트는 인쇄 및 인쇄 미리 보기를 지원합니다.  
  
    -   프로젝트는 ActiveX 컨트롤을 지원합니다.  자세한 내용은 [ActiveX 컨트롤을 만드는 작업 시퀀스](../../mfc/sequence-of-operations-for-creating-activex-controls.md)을 참조하십시오.  
  
    -   프로젝트는 [자동화](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows 소켓](../../mfc/windows-sockets-in-mfc.md) 또는 Active Accessibility를 지원하지 않습니다.  
  
    -   프로젝트는 **탐색기** 도킹 창, **출력** 도킹 창 및 **속성** 도킹 창을 지원합니다.  
  
-   [MFC 응용 프로그램 마법사, 생성된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   프로젝트의 뷰 클래스는 [CView Class](../../mfc/reference/cview-class.md)에서 파생됩니다.  
  
    -   프로젝트의 응용 프로그램 클래스는 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)에서 파생됩니다.  
  
    -   프로젝트의 문서 클래스는 [CDocument Class](../../mfc/reference/cdocument-class.md)에서 파생됩니다.  
  
    -   프로젝트의 주 프레임 클래스는 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)에서 파생됩니다.  
  
    -   프로젝트의 자식 프레임 클래스는 [CMDIChildWndEx 클래스](../../mfc/reference/cmdichildwndex-class.md)에서 파생됩니다.  
  
 기본 설정을 변경하려면 마법사의 왼쪽 열에서 해당하는 탭 제목을 클릭하고 나타나는 페이지에서 필요한 사항을 변경하십시오.  
  
 MFC 응용 프로그램 프로젝트를 만든 후에는 Visual C\+\+ [코드 마법사](../../ide/adding-functionality-with-code-wizards-cpp.md)를 사용하여 프로젝트에 개체 또는 컨트롤을 추가할 수 있습니다.  
  
## 참고 항목  
 [MFC 응용 프로그램 만들기](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)   
 [클래스를 사용하여 Windows 응용 프로그램 작성](../../mfc/using-the-classes-to-write-applications-for-windows.md)