---
title: "다른 언어에 대한 마법사 지원 | Microsoft Docs"
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
  - "vc.appwiz.EastAsianLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC 프로젝트의 언어 지원"
  - "프로젝트[C++], 언어 지원"
  - "마법사[C++], 언어 지원"
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다른 언어에 대한 마법사 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio를 설치할 때 설치 응용 프로그램에서는 시스템에 있는 로캘을 감지하여 적합한 언어 템플릿 또는 해당 로캘용 템플릿을 설치합니다.  예를 들어 서유럽어 로캘이면 영어, 프랑스어, 이탈리아어, 스페인어 및 독일어가 설치됩니다.  이 언어들은 MFC 응용 프로그램 마법사의 [응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지의 **리소스 언어** 목록에 표시됩니다.  
  
## 언어 템플릿  
 템플릿은 ANSI 인코딩을 기반으로 하기 때문에 모든 시스템에 모든 템플릿이 설치되는 것은 아니며 모든 시스템에서 모든 리소스를 편집할 수 있는 것도 아닙니다.  예를 들면 기본적으로 프랑스어 시스템에서는 일본어를 편집할 수 없습니다.  
  
 Windows 2000 이상을 사용하고 있고 다른 언어로 MFC 응용 프로그램을 만들려면 Visual Studio Installer 미디어\(디스크 1\)에서 해당 언어용 템플릿 디렉터리를 시스템에 복사해야 합니다.  
  
> [!NOTE]
>  만들어진 프로젝트를 편집하려면 시스템 로캘을 선택한 언어용 로캘로 설정해야 합니다.  
  
 각 템플릿은 다음 표에서 설명하는 것처럼 \\Microsoft Visual Studio .NET 2003\\Vc7\\VCWizards\\mfcappwiz\\templates\\ 디렉터리의 해당 폴더에 있습니다.  원하는 언어 템플릿에 액세스하려면 해당 폴더를 컴퓨터의 \\mfcappwiz\\templates\\ 디렉터리에 복사합니다.  일단 폴더를 복사하면 그 언어가 MFC 응용 프로그램 마법사의 **응용 프로그램 종류** 페이지에서 **리소스 언어** 목록에 나타납니다.  
  
### Visual Studio .NET에서 제공하는 언어 템플릿  
  
|Language|템플릿|  
|--------------|---------|  
|중국어\(번체\)|1028|  
|중국어\(간체\)|2052|  
|영어|1033|  
|프랑스어|1036|  
|독일어|1031|  
|이탈리아어|1040|  
|일본어|1041|  
|한국어|1042|  
|스페인어|3082|  
  
## Visual C\+\+ 마법사 생성 파일의 형식  
 Visual C\+\+ 마법사는 Visual Studio의 설치된 언어 버전이 시스템 로캘과 일치하지 않을 경우 프로젝트를 유니코드로 생성합니다.  예를 들어, 국가별 설정이 일본어 이외의 언어로 설정된 컴퓨터에 Visual Studio 일본어 버전이 설치되는 경우 Visual C\+\+ 마법사는 유니코드 파일로 구성된 프로젝트를 생성합니다.  이것은 Windows MU\(다국어\) 팩을 사용하여 설치된 컴퓨터에서 일반적입니다.  
  
 이 동작은 시스템 로캘이 Visual Studio의 언어 버전과 동일하게 설치된 시스템에서와는 다릅니다.  이 경우 ANSI로 된 프로젝트 파일이 시스템 코드 페이지에 만들어집니다.  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C\+\+ 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)