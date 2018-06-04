---
title: '방법: 기존 코드로 C++ 프로젝트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1786e5704d7afd07576ab738d907eb841518f8be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330137"
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>방법: 기존 코드로 C++ 프로젝트 만들기

Visual Studio에서 **기존 코드 파일에서 새 프로젝트 만들기** 마법사를 사용하여 기존 코드 파일을 Visual C++ 프로젝트로 이식할 수 있습니다. 이 마법사는 Visual Studio의 이전 Express 버전에서는 사용할 수 없습니다. 이 마법사는 MSBuild 시스템을 사용하여 원본 파일을 관리하고 구성을 빌드하는 새 솔루션과 프로젝트를 만듭니다.  
  
기존 코드 파일을 Visual C++ 프로젝트로 이식하면 IDE에 기본 제공되는 모든 기본 MSBuild 프로젝트 관리 기능을 사용할 수 있습니다. nmake 메이크파일, CMake 또는 대체와 같은 기존 빌드 시스템을 사용하려는 경우, 폴더 열기 옵션을 대신 사용할 수 있습니다. 자세한 내용은 [Visual C++의 폴더 열기 프로젝트](../ide/non-msbuild-projects.md)를 참조하세요. 두 옵션을 모두 사용하면 [IntelliSense](/visualstudio/ide/using-intellisense) 및 [프로젝트 속성](../ide/working-with-project-properties.md)과 같은 IDE 기능을 사용할 수 있습니다.  
  
### <a name="to-create-a-c-project-from-existing-code"></a>기존 코드에서 C++ 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **기존 코드의 프로젝트**를 클릭합니다.  
  
1.  **기존 코드 파일에서 새 프로젝트 만들기** 마법사의 첫 페이지에 있는 **만들 프로젝트 형식** 목록에서 **Visual C++** 를 선택합니다. **다음** 을 선택하여 계속 진행합니다. 
  
1.  프로젝트 위치와 원본 파일의 디렉터리를 지정합니다. 이 페이지에 대한 자세한 내용은 [프로젝트 위치 및 원본 파일 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-project-location-and-source-files.md)를 참조하세요. **다음** 을 선택하여 계속 진행합니다.  
  
1.  사용할 프로젝트 설정을 지정합니다. 이 페이지에 대한 자세한 내용은 [프로젝트 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)를 참조하세요. **다음** 을 선택하여 계속 진행합니다.  

1.  사용할 디버그 구성 설정을 지정합니다. 이 페이지에 대한 자세한 내용은 [디버그 구성 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-debug-configuration-settings.md)를 참조하세요. **다음** 을 선택하여 계속 진행합니다.  

1.  사용할 릴리스 구성 설정을 지정합니다. 이 페이지에 대한 자세한 내용은 [릴리스 구성 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-release-configuration.md)를 참조하세요. **마침**을 선택하여 새 프로젝트를 생성합니다.  
  
## <a name="see-also"></a>참고 항목  

[프로젝트 위치 및 원본 파일 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-project-location-and-source-files.md)   
[프로젝트 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)   
[디버그 구성 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-debug-configuration-settings.md)   
[기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정](../ide/specify-release-configuration.md)