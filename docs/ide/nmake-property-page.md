---
title: "NMake 속성 페이지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs: C++
helpviewer_keywords: NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6c487cf7218f11ba6a6a27ddcf5e7b6b575b1499
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="nmake-property-page"></a>NMake 속성 페이지
**NMake** 속성 페이지 NMake 프로젝트의 빌드 설정을 지정할 수 있습니다.  
  
 NMake 프로젝트에 대 한 자세한 내용은 참조 [메이크파일 프로젝트 만들기](../ide/creating-a-makefile-project.md)합니다.  
  
 **NMake** 속성 페이지에는 다음과 같은 속성이 포함 되어 있습니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **빌드 명령줄**  
 될 때 실행할 명령을 지정 **빌드** 클릭할는 **빌드** 메뉴.  
  
 **모두 다시 빌드 명령줄**  
 될 때 실행할 명령을 지정 **모두 다시 빌드** 클릭할는 **빌드** 메뉴.  
  
 **정리 명령줄**  
 될 때 실행할 명령을 지정 **Clean** 클릭할는 **빌드** 메뉴.  
  
 **출력**  
 명령줄에 대 한 출력을 포함할 파일의 이름을 지정 합니다. 기본적으로이 파일 이름은 프로젝트 이름에 기반 합니다.  
  
 **전처리기 정의**  
 소스 파일에서 사용 하는 전처리기 정의 지정 합니다. 기본값은 현재 플랫폼 및 구성 하 여 결정 됩니다.  
  
 **포함 검색 경로**  
 포함 파일에 대 한 컴파일러 검색 되는 위치는 디렉터리를 지정 합니다.  
  
 **강제 포함**  
 전처리기는 프로젝트 파일에 포함 되지 않는 경우에 자동으로 처리 하는 파일을 지정 합니다.  
  
 **어셈블리 검색 경로**  
 .NET Framework 검색 될 때 디렉터리를 지정 하기.NET 어셈블리를 해결 하려면 바꾸려고 합니다.  
  
 **어셈블리를 사용 하 여 강제**  
 .NET Framework을 자동으로 처리 하는 어셈블리를 지정 합니다.  
  
 **추가 옵션**  
 C + + 파일을 구문 분석할 때 사용할 IntelliSense에 대 한 추가 컴파일러 스위치를 지정 합니다.  
  
 액세스 하는 방법에 대 한 내용은 **NMake** 속성 페이지 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
 프로그래밍 방식으로이 개체의 멤버에 액세스 하는 방법에 대 한 정보를 참조 하십시오. <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [방법: 메이크파일 프로젝트에 IntelliSense 사용](../ide/how-to-enable-intellisense-for-makefile-projects.md)