---
title: 프로젝트 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.appsettings
dev_langs:
- C++
helpviewer_keywords:
- Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0f59b802b5a24c1b449f78cccee4744538a5a0e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33338948"
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정 지정
기존 코드 파일에서 새 프로젝트 만들기 마법사의 이 페이지를 사용하여 다음을 지정합니다.  
  
-   새 프로젝트를 위한 빌드 환경  
  
-   생성할 새 프로젝트의 특정 형식에 맞는 빌드 설정  
  
## <a name="task-list"></a>작업 목록  
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **Visual Studio 사용**  
 새 프로젝트를 빌드할 때 Visual Studio에 포함된 빌드 도구를 사용하도록 지정합니다. 이 옵션은 기본적으로 선택됩니다.  
  
 **프로젝트 형식**  
 마법사가 생성할 프로젝트의 형식을 지정합니다.  
  
 **Windows 응용 프로그램 프로젝트**  
 마법사가 실행 가능한 Windows 응용 프로그램에 대한 프로젝트를 생성함을 나타냅니다. 이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **콘솔 응용 프로그램 프로젝트**  
 마법사가 콘솔 응용 프로그램에 대한 프로젝트를 생성함을 나타냅니다. 이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **DLL(동적 연결 라이브러리) 프로젝트**  
 마법사가 빈 동적 라이브러리 응용 프로그램에 대한 프로젝트를 생성함을 나타냅니다. 이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **LIB(정적 라이브러리) 프로젝트**  
 마법사가 정적 라이브러리 응용 프로그램에 대한 프로젝트를 생성함을 나타냅니다. 이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **ATL에 대한 지원 추가**  
 새 프로젝트에 ATL 지원을 추가합니다.  
  
 **MFC에 대한 지원 추가**  
 새 프로젝트에 MFC 지원을 추가합니다.  
  
 **공용 언어 런타임에 대한 지원 추가**  
 새 프로젝트에 CLR 프로그래밍 지원을 추가합니다.  
  
 **공용 언어 런타임**  
 CLR 기능과 호환되도록 새 프로젝트를 지정합니다.  
  
 **공용 언어 런타임(이전 구문)**  
 Visual C++ 2005 이전의 CLR 프로그래밍 구문인 Managed Extensions for C++ 구문과 호환되도록 새 프로젝트를 지정합니다.  
  
 **외부 빌드 시스템 사용**  
 새 프로젝트를 빌드할 때 Visual Studio에 포함되지 않은 빌드 도구를 사용하도록 지정합니다. 이 옵션을 선택하면 **디버그 구성 설정 지정** 및 **릴리스 구성 설정 지정** 페이지에서 빌드 명령줄을 지정할 수 있습니다.  
  
> [!NOTE]
>  **외부 빌드 시스템 사용** 옵션을 선택하면 IDE가 새 프로젝트를 빌드하지 않으므로 /D, I, /FI, /AI 또는 /FU 옵션을 컴파일할 필요가 없습니다. 그러나 IntelliSense가 제대로 작동하려면 이러한 옵션을 순서대로 올바르게 설정해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 구성 설정 지정, 기존 코드 파일에서 새 프로젝트 만들기 마법사](../ide/specify-debug-configuration-settings.md)   
 [기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정](../ide/specify-release-configuration.md)