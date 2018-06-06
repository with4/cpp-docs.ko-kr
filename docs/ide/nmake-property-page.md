---
title: NMake 속성 페이지(Windows C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs:
- C++
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f156d69467f00c4c4a62ec84d3b870e2999d7115
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33327462"
---
# <a name="nmake-property-page"></a>NMake 속성 페이지
**NMake** 속성 페이지에서 NMake 프로젝트의 빌드 설정을 지정할 수 있습니다.  
  
 NMake 프로젝트에 대한 자세한 내용은 [메이크파일 프로젝트 만들기](../ide/creating-a-makefile-project.md)를 참조하세요. Windows 이외 메이크파일 프로젝트의 경우 [메이크파일 프로젝트 속성(Linux C++)](../linux/prop-pages/makefile-linux.md), [일반 프로젝트 속성(Android C++ 메이크파일)](/visualstudio/cross-platform/general-makefile-android-prop-page) 또는 [NMake 속성(Android C++)](/visualstudio/cross-platform/nmake-android-prop-page)을 참조하세요.
  
 **NMake** 속성 페이지에는 다음 속성이 포함되어 있습니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **빌드 명령줄**  
 **빌드** 메뉴에서 **빌드**를 클릭할 때 실행할 명령을 지정합니다.  
  
 **모두 다시 빌드 명령줄**  
 **빌드** 메뉴에서 **모두 다시 빌드**를 클릭할 때 실행할 명령을 지정합니다.  
  
 **정리 명령줄**  
 **빌드** 메뉴에서 **정리**를 클릭할 때 실행할 명령을 지정합니다.  
  
 **출력**  
 명령줄의 출력을 포함할 파일의 이름을 지정합니다. 기본적으로 이 파일 이름은 프로젝트 이름을 기반으로 합니다.  
  
 **전처리기 정의**  
 원본 파일에서 사용하는 전처리기 정의를 지정합니다. 기본값은 현재 플랫폼 및 구성에 따라 결정됩니다.  
  
 **포함 검색 경로**  
 컴파일러가 포함 파일을 검색하는 디렉터리를 지정합니다.  
  
 **강제 포함**  
 전처리기가 프로젝트 파일에 포함되지 않는 경우에도 자동으로 처리하는 파일을 지정합니다.  
  
 **어셈블리 검색 경로**  
 .NET Framework가 .NET 어셈블리를 확인하려고 할 때 검색하는 디렉터리를 지정합니다.  
  
 **강제 사용 어셈블리**  
 .NET Framework에서 자동으로 처리하는 어셈블리를 지정합니다.  
  
 **추가 옵션**  
 IntelliSense가 C++ 파일을 구문 분석할 때 사용할 추가 컴파일러 스위치를 지정합니다.  
  
 **NMake** 속성 페이지에 액세스하는 방법에 대한 자세한 내용은 [프로젝트 속성 작업](../ide/working-with-project-properties.md)을 참조하세요.  
  
 이 개체의 멤버에 프로그래밍 방식으로 액세스하는 방법에 대한 자세한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [방법: 메이크파일 프로젝트에 IntelliSense 사용](../ide/how-to-enable-intellisense-for-makefile-projects.md)