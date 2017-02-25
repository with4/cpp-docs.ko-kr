---
title: "기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.importwiz.appsettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정"
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 기존 코드 파일에서 새 프로젝트 만들기 마법사, 프로젝트 설정 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기존 코드 파일에서 새 프로젝트 만들기 마법사의 이 페이지를 사용하여 다음을 지정할 수 있습니다.  
  
-   새 프로젝트에 대한 빌드 환경  
  
-   생성할 새 프로젝트의 특정 형식과 일치하는 빌드 설정  
  
## 작업 목록  
 [방법: 기존 코드로 C\+\+ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UI 요소 목록  
 **Visual Studio 사용**  
 Visual Studio에 포함되어 있는 빌드 도구를 새 프로젝트 빌드에 사용하도록 지정합니다.  이 옵션은 기본적으로 선택되어 있습니다.  
  
 **프로젝트 형식**  
 마법사가 생성할 프로젝트의 형식을 지정합니다.  
  
 **Windows 응용 프로그램 프로젝트**  
 마법사가 프로젝트를 실행 가능한 Windows 응용 프로그램으로 생성할 것임을 나타냅니다.  이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **콘솔 응용 프로그램 프로젝트**  
 마법사가 프로젝트를 콘솔 응용 프로그램으로 생성할 것임을 나타냅니다.  이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **DLL\(동적 연결 라이브러리\) 프로젝트**  
 마법사가 프로젝트를 빈 동적 링크 라이브러리 응용 프로그램으로 생성할 것임을 나타냅니다.  이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **정적 라이브러리\(LIB\) 프로젝트**  
 마법사가 프로젝트를 정적 라이브러리 응용 프로그램으로 생성할 것임을 나타냅니다.  이 옵션은 **프로젝트 형식** 드롭다운 목록 상자에서 사용할 수 있습니다.  
  
 **ATL에 대한 지원 추가**  
 새 프로젝트에 ATL 지원을 추가합니다.  
  
 **MFC에 대한 지원 추가**  
 새 프로젝트에 MFC 지원을 추가합니다.  
  
 **공용 언어 런타임에 대한 지원 추가**  
 새 프로젝트에 CLR 프로그래밍 지원을 추가합니다.  
  
 **공용 언어 런타임**  
 새 프로젝트가 CLR 기능 규격을 따르도록 지정합니다.  
  
 **공용 언어 런타임\(이전 구문\)**  
 새 프로젝트가 Visual C\+\+ 2005 이전의 CLR 프로그래밍 구문인 Managed Extensions for C\+\+ 구문의 규격을 따르도록 지정합니다.  
  
 **외부 빌드 시스템 사용**  
 Visual Studio에 포함되어 있지 않은 빌드 도구를 새 프로젝트 빌드에 사용하도록 지정합니다.  이 옵션을 선택하면 **디버그 구성 설정 지정** 및 **릴리스 구성 설정 지정** 페이지에서 빌드 명령줄을 지정할 수 있습니다.  
  
> [!NOTE]
>  **외부 빌드 시스템 사용** 옵션을 선택하면 IDE는 새 프로젝트를 빌드하지 않으므로 컴파일하는 데 \/D, \/I, \/FI, \/AI 또는 \/FU 옵션이 필요하지 않습니다.  하지만 IntelliSense가 제대로 작동하려면 이러한 옵션을 설정해야 합니다.  
  
## 참고 항목  
 [기존 코드 파일에서 새 프로젝트 만들기 마법사, 디버그 구성 설정 지정](../ide/specify-debug-configuration-settings.md)   
 [기존 코드 파일에서 새 프로젝트 만들기 마법사, 릴리스 구성 설정 지정](../ide/specify-release-configuration.md)