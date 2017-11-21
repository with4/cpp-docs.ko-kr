---
title: "VC + + 디렉터리 속성 페이지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs: C++
helpviewer_keywords: VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30a54b1d90585e6433f059acf30991ca53948d60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="vc-directories-property-page"></a>VC++ 디렉터리 속성 페이지
Visual Studio 프로젝트를 빌드하는 데 사용할 디렉터리를 지정합니다. 이 속성 페이지에 액세스 하려면 **솔루션 탐색기**를 프로젝트에 대 한 바로 가기 메뉴를 열고 선택 **속성**, 한 다음의 왼쪽된 창에서 **속성 페이지** 대화 상자에서 **구성 속성** 선택 **VC + + 디렉터리**합니다.  
  
 Visual Studio를 사용하여 프로젝트를 만들 때, 특정 디렉터리를 상속합니다. 이들 중 대부분은 매크로로 지정됩니다. 오른쪽 창에서 매크로의 현재 값을 검사 하는 **VC + + 디렉터리** 페이지에서 행을 선택-예를 들어 **포함 디렉터리**-오른쪽에서 아래쪽 화살표 단추를 선택, 선택  **편집**, 한 후 표시 되는 대화 상자에서 선택 된 **매크로** 단추입니다. 자세한 내용은 다음 블로그 게시물을 참조 하십시오.: [VC + + 디렉터리](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [상속 된 속성 및 속성 시트](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), 및 [Visual Studio 2010 c + + 프로젝트 업그레이드 가이드](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx)합니다.  
  
## <a name="directory-types"></a>디렉터리 형식  
 다음과 같이 다른 디렉터리를 지정할 수도 있습니다.  
  
 **실행 가능 디렉터리**  
 실행 파일을 검색할 디렉터리입니다. 에 해당 하는 **경로** 환경 변수입니다.  
  
 **포함 디렉터리**  
 소스 코드에서 참조되는 포함 파일을 검색할 디렉터리입니다. 에 해당 하는 **INCLUDE** 환경 변수입니다.  
  
 **참조 디렉터리**  
 디렉터리를 검색 하 여 소스 코드에서 참조 되는 어셈블리 및 모듈 (메타 데이터)에 [#using](../preprocessor/hash-using-directive-cpp.md) 지시문입니다. 에 해당 하는 **LIBPATH** 환경 변수입니다.  
  
 **라이브러리 디렉터리**  
 라이브러리(.lib) 파일을 검색할 디렉터리입니다. 여기에는 런타임 라이브러리가 포함됩니다. 에 해당 하는 **LIB** 환경 변수입니다. 이 설정은.obj 파일에 적용 되지 않습니다. .obj 파일에 연결 하는 [링커](../ide/linker-property-pages.md)**일반** 속성 페이지 **추가 라이브러리 종속성** 한 다음 파일의 상대 경로 지정 합니다.  
  
 **원본 디렉터리**  
 IntelliSense에 사용할 소스 파일을 검색할 디렉터리입니다.  
  
 **디렉터리 제외**  
 빌드 종속성을 확인할 때 검색하지 않을 디렉터리입니다.  
  
#### <a name="to-specify-or-modify-directory-settings"></a>디렉터리 설정을 지정 또는 수정하려면  
  
1.  **솔루션 탐색기**, 다음을 선택 하 고 변경 하려는 프로젝트에 대 한 바로 가기 메뉴를 열고 **속성**합니다.  
  
2.  왼쪽된 창에는 **속성 페이지** 대화 상자에서 **구성 속성** 선택한 후 **VC + + 디렉터리**합니다.  
  
3.  디렉터리 목록 중 하나를 수정, 선택 하 고, 오른쪽에서 아래쪽 화살표 단추를 선택 하 고 다음 선택 하려면 **편집**합니다.  
  
     나타나는 대화 상자에서 값을 추가하거나 제거할 수 있고 값이 나타나는 순서를 다시 정렬할 수 있습니다. 프로젝트 선택 하거나 선택 취소 하 여 모든 설정을 상속 하는지를 변경할 수도 있습니다 **부모 또는 프로젝트 기본값에서 상속**합니다.  
  
## <a name="sharing-the-settings"></a>설정 공유  
 프로젝트 속성을 다른 사용자 또는 여러 컴퓨터와 공유할 수 있습니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
