---
title: "기존 코드 파일 마법사에서 새 프로젝트를 만들 프로젝트 설정 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.appsettings
dev_langs: C++
helpviewer_keywords: Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cf1e8eba11063f7f2e46f836cd2ef84cc70dfe8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정 지정
기존 코드 파일에서 새 프로젝트 만들기 마법사의이 페이지를 사용 하 여 지정할 수 있습니다.  
  
-   새 프로젝트에 대 한 빌드 환경  
  
-   빌드를 생성 하는 새 프로젝트의 특정 유형과 일치 하도록 설정  
  
## <a name="task-list"></a>작업 목록  
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **Visual Studio 사용**  
 새 프로젝트를 빌드하기 위해 Visual Studio에 포함 된 빌드 도구를 사용 하도록 지정 합니다. 이 옵션은 기본적으로 선택됩니다.  
  
 **프로젝트 형식**  
 마법사가 생성 된 프로젝트의 유형을 지정 합니다.  
  
 **Windows 응용 프로그램 프로젝트**  
 마법사가 실행 가능한 Windows 응용 프로그램에 대 한 프로젝트를 생성할 나타냅니다. 이 옵션은 사용할 수는 **프로젝트 형식** 드롭다운 목록 상자입니다.  
  
 **콘솔 응용 프로그램 프로젝트**  
 마법사는 콘솔 응용 프로그램에 대 한 프로젝트를 생성 함을 나타냅니다. 이 옵션은 사용할 수는 **프로젝트 형식** 드롭다운 목록 상자입니다.  
  
 **동적 연결된 라이브러리 (DLL) 프로젝트**  
 마법사는 빈 동적 연결 라이브러리 응용 프로그램에 대 한 프로젝트를 생성 함을 나타냅니다. 이 옵션은 사용할 수는 **프로젝트 형식** 드롭다운 목록 상자입니다.  
  
 **정적 라이브러리 (LIB) 프로젝트**  
 마법사는 정적 라이브러리 응용 프로그램에 대 한 프로젝트를 생성 함을 나타냅니다. 이 옵션은 사용할 수는 **프로젝트 형식** 드롭다운 목록 상자입니다.  
  
 **ATL에 대 한 지원 추가**  
 새 프로젝트에 ATL 지원을 추가합니다.  
  
 **MFC에 대 한 지원 추가**  
 새 프로젝트에 MFC 지원을 추가합니다.  
  
 **공용 언어 런타임에 대 한 지원 추가**  
 새 프로젝트에 CLR 프로그래밍 지원을 추가 합니다.  
  
 **공용 언어 런타임**  
 CLR 기능과 호환 되도록 새 프로젝트를 지정 합니다.  
  
 **공용 언어 런타임 (이전 구문)**  
 새 프로젝트는 Visual c + + 2005 이전 CLR 프로그래밍 구문이 c + + 구문에 대 한 Managed Extensions과 호환 되도록 지정 합니다.  
  
 **외부 빌드 시스템을 사용 하 여**  
 새 프로젝트를 빌드하기 위해 Visual Studio에 포함 되지 않은 빌드 도구를 사용 하도록 지정 합니다. 이 옵션을 선택 하는 경우에 빌드 명령줄을 지정할 수 있습니다는 **디버그 구성 설정 지정** 및 **릴리스 구성 설정 지정** 페이지입니다.  
  
> [!NOTE]
>  경우는 **외부 빌드 시스템 사용** 옵션을 선택, IDE에 새 프로젝트를 빌드하지 않습니다 하므로 /D, I, /FI, /AI 또는 /FU 옵션 컴파일에 필요 하지 않은 /입니다. 그러나 이러한 옵션 intellisense가 제대로 작동 하려면 순서 대로 올바르게 설정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기존 코드 파일 마법사에서 새 프로젝트 만들기, 디버그 구성 설정 지정](../ide/specify-debug-configuration-settings.md)   
 [기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정](../ide/specify-release-configuration.md)