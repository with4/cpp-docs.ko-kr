---
title: "Visual C++ 프로젝트 형식 | Microsoft Docs"
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
  - "프로그램[C++], 프로젝트"
  - "프로젝트 템플릿[Visual Studio], C++"
  - "TODO 주석[C++]"
  - "프로젝트[C++], 형식"
  - "템플릿[C++], 프로젝트"
  - "응용 프로그램[C++], 프로젝트"
  - "Visual C++ 프로젝트, 형식"
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ 프로젝트 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트 템플릿을 사용하면 만들려는 프로젝트의 종류에 적합한 기본 프로그램 구조, 메뉴, 도구 모음, 아이콘, 참조 및 `#include` 문을 만들 수 있습니다. Visual Studio는 여러 종류의 Visual C\+\+ 프로젝트 템플릿을 포함하며 대부분의 템플릿에 대해 마법사를 제공하므로 프로젝트를 만들면서 사용자 지정할 수 있습니다. 프로젝트를 만든 직후에 응용 프로그램을 빌드하고 실행할 수 있으므로, 응용 프로그램을 개발하면서 간간이 빌드하는 것이 좋습니다.  
  
 프로젝트를 만드는 데 템플릿을 사용할 필요는 없지만 대부분의 경우에는 템플릿을 사용하는 것이 더 효율적입니다. 프로젝트 파일과 구조를 새로 만드는 것보다는 제공된 프로젝트 파일과 구조를 수정하는 것이 더 쉽기 때문입니다.  
  
> [!NOTE]
>  C\+\+ 프로젝트 템플릿을 사용하여 C 언어 프로젝트를 만들 수 있습니다. 생성된 프로젝트에서 파일 이름 확장명이 .cpp인 파일을 찾아 확장명을 .c로 변경합니다. 그런 다음 솔루션이 아닌 프로젝트의 **프로젝트 속성** 페이지에서 **구성 속성**, **C\/C\+\+**를 차례로 확장하고 **고급**을 선택합니다.**컴파일 옵션** 설정을 **C 코드로 컴파일\(\/TC\)**로 변경합니다.  
  
## 프로젝트 템플릿  
 Visual Studio에는 다음 Visual C\+\+ 프로젝트 템플릿이 포함되어 있습니다.  
  
### 스토어 앱  
  
||  
|-|  
|[스토어 앱에 대한 C\#, VB 및 C\+\+ 프로젝트 템플릿](http://go.microsoft.com/fwlink/p/?LinkID=262279)|  
  
### ATL  
  
|프로젝트 템플릿|프로젝트를 만드는 방법|  
|--------------|------------------|  
|ATL 프로젝트|[ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md)|  
  
### CLR  
  
|프로젝트 템플릿|  
|--------------|  
|[\(NOTINBUILD\)클래스 라이브러리 템플릿\(C\+\+\)](http://msdn.microsoft.com/ko-kr/0d779bfa-5c5a-4b10-a9d5-a6791764a78f)|  
|[방법: CLR 콘솔 응용 프로그램 만들기](../dotnet/how-to-create-clr-console-applications-cpp-cli.md)|  
|[NOTINBUILD CLR 빈 프로젝트 템플릿\(C\+\+\)](http://msdn.microsoft.com/ko-kr/f57c5572-5581-440f-b684-eec646764f08)|  
  
### 일반  
  
|프로젝트 템플릿|프로젝트를 만드는 방법|  
|--------------|------------------|  
|빈 프로젝트|[솔루션 및 프로젝트 만들기](../Topic/Creating%20Solutions%20and%20Projects.md)|  
|사용자 지정 마법사|[사용자 지정 마법사 만들기](../ide/creating-a-custom-wizard.md)|  
|메이크파일 프로젝트|[메이크파일 프로젝트 만들기](../ide/creating-a-makefile-project.md)|  
  
### MFC  
  
|프로젝트 템플릿|프로젝트를 만드는 방법|  
|--------------|------------------|  
|MFC ActiveX 컨트롤|[MFC ActiveX 컨트롤 만들기](../mfc/reference/creating-an-mfc-activex-control.md)|  
|MFC 응용 프로그램|[MFC 응용 프로그램 만들기](../mfc/reference/creating-an-mfc-application.md)|  
|MFC DLL|[MFC DLL 프로젝트 만들기](../mfc/reference/creating-an-mfc-dll-project.md)|  
  
### 테스트  
  
|프로젝트 템플릿|프로젝트를 만드는 방법|  
|--------------|------------------|  
|관리되는 테스트 프로젝트|[단위 테스트 프로젝트 만들기](../Topic/Create%20a%20unit%20test%20project.md)|  
|기본 단위 테스트 프로젝트|[테스트 탐색기를 사용하여 네이티브 코드 단위 테스트](http://msdn.microsoft.com/ko-kr/8a09d6d8-3613-49d8-9ffe-11375ac4736c)|  
  
### Win32  
  
|프로젝트 템플릿|프로젝트를 만드는 방법|  
|--------------|------------------|  
|Win32 콘솔 프로젝트|[콘솔 응용 프로그램 만들기](../windows/creating-a-console-application.md)|  
|Win32 프로젝트|[방법: Windows 데스크톱 응용 프로그램 만들기](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)|  
  
## TODO 주석  
 프로젝트 템플릿에서 생성하는 대부분의 파일은 원하는 소스 코드를 입력할 위치를 확인할 수 있도록 TODO 주석을 포함합니다. 코드를 추가하는 방법에 대한 자세한 내용은 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md) 및 [Working with Resource Files](../mfc/working-with-resource-files.md)을 참조하세요.  
  
## 참고 항목  
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [프로젝트를 사용하여 응용 프로그램 만들기](http://msdn.microsoft.com/ko-kr/3339fa90-bac2-4b95-8361-662a2e0e7dfe)   
 [CLR 프로젝트](../ide/files-created-for-clr-projects.md)