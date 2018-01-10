---
title: "방법: 기존 코드에서 c + + 프로젝트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6781709c105c606f6ceb856654525385738c1ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>방법: 기존 코드로 C++ 프로젝트 만들기

Visual Studio에서 있습니다 수 기존 코드 파일 Visual c + + 프로젝트에 사용 하 여 포트는 **기존 코드 파일에서 새 프로젝트 만들기** 마법사. 이 마법사는 이전 Visual Studio Express edition에서 사용할 수 없습니다. 이 마법사는 새 솔루션 및 소스 파일을 관리 하 고 빌드 구성에는 MSBuild 시스템을 사용 하는 프로젝트를 만듭니다.  
  
Visual c + + 프로젝트에 기존 코드 파일을 이식 모든 IDE에 기본 제공 기본 MSBuild 프로젝트 관리 기능을 사용할 수 있습니다. Nmake 메이크파일, CMake, 대체 등 기존 빌드 시스템을 사용 하는 것을 선호 하는 경우에 열려 있는 폴더 옵션 대신 사용할 수 있습니다. 자세한 내용은 [Visual C++의 폴더 열기 프로젝트](../ide/non-msbuild-projects.md)를 참조하세요. 두 옵션을 사용 하면 같은 IDE 기능을 사용 하 여 [IntelliSense](/visualstudio/ide/using-intellisense) 및 [프로젝트 속성](../ide/working-with-project-properties.md)합니다.  
  
### <a name="to-create-a-c-project-from-existing-code"></a>기존 코드에서 C++ 프로젝트를 만들려면  
  
1.  에 **파일** 메뉴에서 **새로**, 클릭 하 고 **기존 코드의 프로젝트**합니다.  
  
1.  첫 번째 페이지의 **기존 코드 파일에서 새 프로젝트 만들기** 선택 마법사 **Visual c + +** 에 **어떤 유형의 프로젝트를 만드는 시겠습니까** 목록입니다. **다음** 을 선택하여 계속 진행합니다. 
  
1.  프로젝트 위치 및 소스 파일의 디렉터리를 지정 합니다. 이 페이지에 세부 정보를 참조 하십시오. [프로젝트 위치 지정 및 소스 파일을 새 프로젝트에서 기존 코드 파일 만들기 마법사](../ide/specify-project-location-and-source-files.md)합니다. **다음** 을 선택하여 계속 진행합니다.  
  
1.  프로젝트 설정을 사용 하도록 지정 합니다. 이 페이지에 세부 정보를 참조 하십시오. [프로젝트 설정 지정, 새 프로젝트에서 기존 코드 파일 만들기 마법사](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)합니다. **다음** 을 선택하여 계속 진행합니다.  

1.  디버그 구성 설정을 사용 하도록 지정 합니다. 이 페이지에 세부 정보를 참조 하십시오. [디버그 구성 설정 지정, 새 프로젝트에서 기존 코드 파일 만들기 마법사](../ide/specify-debug-configuration-settings.md)합니다. **다음** 을 선택하여 계속 진행합니다.  

1.  릴리스 구성 설정을 사용 하도록 지정 합니다. 이 페이지에 세부 정보를 참조 하십시오. [릴리스 구성 설정 지정, 새 프로젝트에서 기존 코드 파일 만들기 마법사](../ide/specify-release-configuration.md)합니다. 선택 **마침** 새 프로젝트를 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  

[프로젝트를 지정 위치 및 소스 파일을 기존 코드 파일 마법사에서 새 프로젝트 만들기](../ide/specify-project-location-and-source-files.md)   
[기존 코드 파일 마법사에서 새 프로젝트 만들기, 프로젝트 설정 지정](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)   
[기존 코드 파일 마법사에서 새 프로젝트 만들기, 디버그 구성 설정 지정](../ide/specify-debug-configuration-settings.md)   
[기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정](../ide/specify-release-configuration.md)