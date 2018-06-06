---
title: Visual C++ 프로젝트용 파일 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header files [C++], Visual C++ projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7158e729d80d8b0456862ee6418f039b7f948fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336019"
---
# <a name="file-types-created-for-visual-c-projects"></a>Visual C++ 프로젝트용으로 만들어지는 파일 형식
이 항목에서는 클래식 데스크톱 응용 프로그램용 Visual C++ 프로젝트와 관련된 파일의 모든 형식에 대해 설명합니다. 프로젝트 형식 및 마법사에서 선택한 옵션에 따라 프로젝트에 포함되는 실제 파일이 달라집니다.  
  
-   [프로젝트 및 솔루션 파일](../ide/project-and-solution-files.md)  
  
-   [CLR 프로젝트](../ide/files-created-for-clr-projects.md)  
  
-   [ATL 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/atl-program-or-control-source-and-header-files.md)  
  
-   [MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../ide/mfc-program-or-control-source-and-header-files.md)  
  
-   [미리 컴파일된 헤더 파일](../ide/precompiled-header-files.md)  
  
-   [리소스 파일](../ide/resource-files-cpp.md)  
  
-   [도움말 파일(WinHelp)](../ide/help-files-winhelp.md)  
  
-   [힌트 파일](../ide/hint-files.md)  
  
 [Visual C++ 프로젝트를 만들 때](../ide/creating-desktop-projects-by-using-application-wizards.md)새 솔루션을 만들거나 솔루션에 프로젝트를 추가할 수 있습니다. 중요 응용 프로그램은 일반적으로 솔루션의 여러 프로젝트로 개발됩니다.  
  
 프로젝트는 보통 EXE 또는 DLL을 생성합니다. 프로젝트는 서로 종속될 수 있습니다. 빌드 프로세스 중에 Visual C++ 환경에서 프로젝트 내부 및 프로젝트 간의 종속성을 모두 검사합니다. 각 프로젝트에는 핵심 소스 코드가 있으며, 그 밖에 프로젝트 종류에 따라 프로젝트의 다양한 측면을 포함하는 많은 파일이 있을 수 있습니다. 이러한 파일의 내용은 파일 확장명으로 표시됩니다. Visual Studio 개발 환경에서는 빌드하는 동안 파일 확장명을 사용하여 파일 내용을 처리할 방법을 결정합니다.  
  
 다음 표에는 Visual C++ 프로젝트의 일반적인 파일과 해당 확장명이 나와 있습니다.  
  
|파일 확장명|형식|목차|  
|--------------------|----------|--------------|  
|.asmx|소스|배포 파일|  
|.asp|소스|Active Server Page 파일|  
|.asp|프로젝트|응용 프로그램 템플릿 프로젝트 파일|  
|.bmp, .dib, .gif, .jpg, .jpe, .png|리소스|일반 이미지 파일|  
|.bsc|컴파일|브라우저 코드 파일|  
|.cpp, .c|소스|응용 프로그램의 기본 소스 코드 파일|  
|.cur|리소스|커서 비트맵 그래픽 파일|  
|.dbp|프로젝트|데이터베이스 프로젝트 파일|  
|.disco|소스|동적 검색 문서 파일. XML Web services 검색을 처리합니다.|  
|.exe, .dll|프로젝트|실행 파일 또는 동적 연결 라이브러리 파일|  
|.h|소스|헤더(포함) 파일|  
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|리소스|공용 웹 파일|  
|.HxC|프로젝트|도움말 프로젝트 파일|  
|.ico|리소스|아이콘 비트맵 그래픽 파일|  
|.idb|컴파일|소스 파일과 클래스 정의 간의 종속성 정보가 포함된 상태 파일. 최소 다시 빌드 및 증분 컴파일 중에 컴파일러에 의해 사용될 수 있습니다. .idb 이름을 지정하려면 [/Fd](../build/reference/fd-program-database-file-name.md) 컴파일러 옵션을 사용합니다. 자세한 내용은 [/Gm(최소 다시 빌드 가능)](../build/reference/gm-enable-minimal-rebuild.md) 을 참조하세요.|  
|.idl|컴파일|IDL(Interface Definition Language) 파일. 자세한 내용은 Windows SDK의 [인터페이스 정의(IDL) 파일](http://msdn.microsoft.com/library/windows/desktop/aa378712)을 참조하세요.|  
|.ilk|연결|증분 링크 파일. 자세한 내용은 [/INCREMENTAL](../build/reference/incremental-link-incrementally.md) 을 참조하세요.|  
|.map|연결|링커 정보가 포함된 텍스트 파일. 맵 파일 이름을 지정하려면 [/Fm](../build/reference/fm-name-mapfile.md) 컴파일러 옵션을 사용합니다. 자세한 내용은 [/MAP](../build/reference/map-generate-mapfile.md) 을 참조하세요.|  
|.mfcribbon-ms|리소스|리본의 단추, 컨트롤 및 특성을 정의하는 XML 코드가 포함된 리소스 파일. 자세한 내용은 [Ribbon Designer (MFC)](../mfc/ribbon-designer-mfc.md)을 참조하세요.|  
|.obj, .o||컴파일되었지만 연결되지 않은 개체 파일|  
|.pch|디버그|미리 컴파일된 헤더 파일|  
|.rc, .rc2|리소스|리소스를 생성하는[리소스 스크립트 파일](../windows/working-with-resource-files.md) |  
|.sbr|컴파일|소스 브라우저 중간 파일. [BSCMAKE](../build/reference/bscmake-options.md)의 입력 파일입니다.|  
|.sln|솔루션|[솔루션](http://msdn.microsoft.com/en-us/a45c299d-69f5-4b67-879d-1383417df0a7) 파일|  
|.suo|솔루션|솔루션 옵션 파일|  
|.txt|리소스|텍스트 파일(일반적으로 "추가 정보" 파일)|  
|.vap|프로젝트|Visual Studio Analyzer 프로젝트 파일|  
|.vbg|솔루션|호환 가능한 프로젝트 그룹 파일|  
|.vbp, .vip, .vbproj|프로젝트|Visual Basic 프로젝트 파일|  
|.vcxitems|프로젝트|여러 C++ 프로젝트 간에 코드 파일을 공유하는 공유 항목 프로젝트입니다. 자세한 내용은 [프로젝트 파일 및 메이크파일](../ide/project-and-solution-files.md) 을 참조하세요.|
|.vcxproj|프로젝트|Visual C++ 프로젝트 파일. 자세한 내용은 [프로젝트 파일 및 메이크파일](../ide/project-and-solution-files.md) 을 참조하세요.|  
|.vcxproj.filters|프로젝트|솔루션 탐색기를 사용하여 프로젝트에 파일을 추가하는 경우 필터 파일은 솔루션 탐색기 트리 뷰에서 해당 파일 이름 확장명에 따라 파일이 추가되는 위치를 정의합니다.|  
|.vdproj|프로젝트|Visual Studio 배포 프로젝트 파일|  
|.vmx|프로젝트|매크로 프로젝트 파일|  
|.vup|프로젝트|유틸리티 프로젝트 파일.|  
  
 Visual Studio와 관련된 다른 파일에 대한 자세한 내용은 [Visual Studio.NET의 파일 형식 및 파일 확장명](/visualstudio/ide/reference/project-and-solution-file-types)을 참조하세요.  
  
 프로젝트 파일은 솔루션 탐색기에서 폴더로 구성됩니다. Visual C++는 소스 파일, 헤더 파일 및 리소스 파일의 폴더를 만들지만 이러한 폴더를 다시 구성하거나 새로 만들 수 있습니다. 폴더를 사용하여 프로젝트 계층 내에서 파일의 논리적 클러스터를 명시적으로 구성할 수 있습니다. 예를 들어 모든 사용자 인터페이스 소스 파일 또는 사양, 문서, 테스트 도구 모음 등을 포함하는 폴더를 만들 수 있습니다. 모든 파일 폴더 이름은 고유해야 합니다.  
  
 프로젝트에 항목을 추가하면 항목을 빌드할 수 있는지 여부에 상관없이 해당 프로젝트의 모든 구성에 항목이 추가됩니다. 예를 들어 MyProject라는 프로젝트가 있는 경우 항목을 추가하면 디버그 및 릴리스 프로젝트 구성 둘 다에 항목이 추가됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C++ 프로젝트 형식](../ide/visual-cpp-project-types.md)   
 [다른 언어에 대한 마법사 지원](../ide/wizard-support-for-other-languages.md)