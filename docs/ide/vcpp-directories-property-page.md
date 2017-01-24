---
title: "VC++ 디렉터리 속성 페이지 | Microsoft Docs"
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
  - "VC.Project.VCDirectories.IncludePath"
  - "VC.Project.VCDirectories.ReferencePath"
  - "VC.Project.VCDirectories.SourcePath"
  - "VC.Project.VCDirectories.LibraryWPath"
  - "VC.Project.VCDirectories.ExecutablePath"
  - "VC.Project.VCDirectories.LibraryPath"
  - "VS.ToolsOptionsPages.Projects.VCDirectories"
  - "VC.Project.VCDirectories.ExcludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VC++ 디렉터리 속성 페이지"
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VC++ 디렉터리 속성 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio 프로젝트를 빌드하는 데 사용할 디렉터리를 지정합니다.  이 속성 페이지에 액세스하려면 **솔루션 탐색기**에서 프로젝트에 대한 바로 가기 메뉴를 열고 **속성**을 선택한 후, **속성 페이지** 대화 상자의 왼쪽 창에서, **구성 속성**을 확장하고, **VC\+\+ 디렉터리**를 선택합니다.  
  
 Visual Studio를 사용하여 프로젝트를 만들 때, 특정 디렉터리를 상속합니다.  이들 중 대부분은 매크로로 지정됩니다.  매크로의 현재 값을 조사하려면 **VC\+\+ 디렉터리** 페이지의 오른쪽 창에서 행을 선택합니다. 예를 들어 **포함 디렉터리**의 경우 오른쪽의 아래쪽 화살표 단추를 선택하고 **편집**을 선택한 다음 나타나는 대화 상자에서 **매크로** 단추를 선택합니다.  자세한 내용은 [VC\+\+ 디렉터리](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [상속된 속성 및 속성 시트](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx) 및 [Visual Studio 2010 C\+\+ 프로젝트 업그레이드 가이드](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) 블로그 게시물을 참조하십시오.  
  
## 디렉터리 형식  
 다음과 같이 다른 디렉터리를 지정할 수도 있습니다.  
  
 **실행 가능 디렉터리**  
 실행 파일을 검색할 디렉터리입니다.  **PATH** 환경 변수에 해당합니다.  
  
 **포함 디렉터리**  
 소스 코드에서 참조되는 포함 파일을 검색할 디렉터리입니다.  **INCLUDE** 환경 변수에 해당합니다.  
  
 **참조 디렉터리**  
 소스 코드에서 [\#using](../preprocessor/hash-using-directive-cpp.md) 지시문으로 참조되는 어셈블리 및 모듈\(메타데이터\) 파일을 검색할 디렉터리입니다.  **LIBPATH** 환경 변수에 해당합니다.  
  
 **라이브러리 디렉터리**  
 라이브러리\(.lib\) 파일을 검색할 디렉터리입니다. 여기에는 런타임 라이브러리가 포함됩니다.  **LIB** 환경 변수에 해당합니다.  이 설정은 .obj 파일에 적용되지 않습니다. .obj 파일에 연결하려면 [링커](../ide/linker-property-pages.md) **일반** 속성 페이지에서 **추가 라이브러리 종속성**을 선택한 다음 파일의 상대 경로를 지정합니다.  
  
 **소스 디렉터리**  
 IntelliSense에 사용할 소스 파일을 검색할 디렉터리입니다.  
  
 **디렉터리 제외**  
 빌드 종속성을 확인할 때 검색하지 않을 디렉터리입니다.  
  
#### 디렉터리 설정을 지정 또는 수정하려면  
  
1.  **솔루션 탐색기**에서 변경하려는 프로젝트의 바로 가기 메뉴를 연 다음 **속성**을 선택합니다.  
  
2.  **속성 페이지** 대화 상자의 왼쪽 창에서, **구성 속성**을 확장한 다음 **VC\+\+ 디렉터리**를 선택합니다.  
  
3.  디렉터리 목록 중 하나를 수정하려면 목록을 선택하고 오른쪽의 아래쪽 화살표 단추를 선택한 다음 **편집**을 선택합니다.  
  
     나타나는 대화 상자에서 값을 추가하거나 제거할 수 있고 값이 나타나는 순서를 다시 정렬할 수 있습니다.  **부모 또는 프로젝트 기본값에서 상속**을 선택 또는 취소하여 프로젝트가 설정을 상속하는지를 변경할 수도 있습니다.  
  
## 설정 공유  
 프로젝트 속성을 다른 사용자 또는 여러 컴퓨터와 공유할 수 있습니다.  자세한 내용은 [프로젝트 속성 사용](../ide/working-with-project-properties.md)을 참조하십시오.  
  
## 참고 항목  
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)