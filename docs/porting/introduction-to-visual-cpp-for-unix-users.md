---
title: "UNIX 사용자를 위한 Visual C++ 소개 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UNIX [C++]"
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# UNIX 사용자를 위한 Visual C++ 소개
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]를 처음 사용하며 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]로 생산성을 높이려는 UNIX 사용자에게 정보를 제공합니다.  
  
## 명령줄에서 시작  
 UNIX 명령줄 환경을 사용하는 것과 유사한 방식으로 명령줄에서 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]를 사용할 수 있습니다.  명령줄 C 및 C\+\+ 컴파일러\(CL.EXE\)와 UNIX에서 만든 유틸리티의 Microsoft 버전인 NMAKE.EXE를 비롯한 도구를 사용하여 명령 프롬프트에서 컴파일합니다.  
  
 UNIX에서는 \/usr\/bin 등의 공용 폴더에 명령이 설치됩니다.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]에서는 설치 디렉터리의 VC\\bin\(일반 설치의 경우 Program Files\\Microsoft Visual Studio 8\\VC\\bin\)에 명령줄 도구가 설치됩니다.  명령줄 도구를 사용하려면 설치 디렉터리의 Common7\\Tools에 있는 vsvars32.bat를 실행합니다.  그러면 경로에 bin 디렉터리가 추가되고 명령줄에서 Visual C\+\+ 프로그램을 컴파일하는 데 필요한 기타 경로가 설정됩니다.  
  
> [!NOTE]
>  **시작** 메뉴에서 **Visual Studio 명령줄 프롬프트**를 사용하여 명령 프롬프트를 열면 vsvars32.bat가 실행됩니다.  
  
 디버거, 문 완성 등의 보다 강력한 기능을 활용하려면 개발 환경을 사용해야 합니다.  자세한 내용은 [명령줄 빌드](../build/building-on-the-command-line.md) 및 [연습: 명령줄에서 네이티브 C\+\+ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)을 참조하세요.  
  
## 코드 디버그  
 명령줄을 사용하고 개발용 워크스테이션에서 응용 프로그램을 실행하는 경우 코드에서 메모리 액세스 위반, 처리되지 않은 예외 또는 기타 복구할 수 없는 오류가 발생할 때 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 디버거를 실행하는 대화 상자가 표시되는 것을 확인할 수 있습니다.  **확인**을 클릭하면 Visual Studio 개발 환경이 시작되고 디버거가 오류 지점에서 열립니다.  이러한 방식으로 응용 프로그램을 디버그할 수 있으며, 이 경우 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../build/reference/z7-zi-zi-debug-information-format.md) 스위치로 컴파일한 경우에만 소스 코드를 사용할 수 있습니다.  자세한 내용은 [네이티브 코드 디버깅](../Topic/Debugging%20Native%20Code.md) 및 [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)를 참조하세요.  
  
## 개발 환경 사용  
 개발 환경을 사용하면 *프로젝트*의 소스 코드를 보다 쉽게 편집 및 빌드할 수 있습니다.  프로젝트는 라이브러리 또는 실행 파일과 같은 하나의 단위로 컴파일되는 소스 및 관련 파일의 컬렉션입니다.  또한 프로젝트에는 파일을 빌드하는 방법에 대한 정보도 들어 있습니다.  프로젝트 정보는 확장명이 .prj인 프로젝트 파일에 저장됩니다.  
  
 잠재적으로 각각 다른 컴파일러 옵션 집합이나 다른 언어로 빌드된 여러 라이브러리와 실행 파일로 구성된 응용 프로그램은 단일 *솔루션*에 속하는 여러 프로젝트에 저장됩니다.  솔루션은 여러 프로젝트를 함께 그룹화하는 컨테이너에 대한 추상화입니다.  솔루션 정보는 확장명이 .sln 솔루션 파일에 저장됩니다.  자세한 내용은 [PAVE: Managing Solutions and Projects](http://msdn.microsoft.com/ko-kr/7a50db22-d3cc-46f3-b648-ab7e0528e260) 및 [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)를 참조하세요.  
  
## 기존 코드 가져오기  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]를 통해 메이크파일을 포함하거나 포함하지 않고 컴파일하도록 설정된 기존 코드를 사용하고 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 프로젝트에 넣을 수 있습니다.  자세한 내용은 **기존 코드 파일에서 프로젝트 만들기 마법사**를 참조하세요.  자세한 내용은 [방법: 기존 코드로 C\+\+ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)를 참조하세요.  
  
## 새 프로젝트 만들기  
 개발 환경에서 새 프로젝트를 만들 수 있습니다.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]에서는 여러 일반적인 프로젝트에 대한 표준 코드를 제공하는 다양한 템플릿을 제공합니다.  응용 프로그램 마법사를 사용하여 다양한 응용 프로그램 형식에 대한 코드 개요로 프로젝트를 생성할 수 있습니다.  
  
 **콘솔 응용 프로그램\(Win32\) 마법사**를 사용하면 빈 프로젝트로 시작할 수 있습니다.  **빈 프로젝트** 확인란을 선택합니다.  나중에 프로젝트에 새 파일과 기존 파일을 추가할 수 있습니다.  
  
 프로젝트를 만들 때 프로젝트에 이름을 지정해야 합니다.  기본적으로 프로젝트 이름은 프로젝트에서 빌드된 DLL\(동적 연결 라이브러리\) 또는 실행 파일의 이름과 같습니다.  자세한 내용은 [솔루션 및 프로젝트 만들기](../Topic/Creating%20Solutions%20and%20Projects.md)를 참조하세요.  
  
## Microsoft 전용 한정자  
 Visual C\+\+에는 표준 C\+\+ 프로그래밍 언어에 대한 여러 확장이 포함되어 있습니다.  이러한 확장은 특히 저장소 클래스 특성, 함수 호출 규칙 및 기본 주소를 지정하는 데 사용됩니다.  모든 Visual C\+\+ 확장의 전체 목록은 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)를 참조하세요.  
  
 **\/Za** 컴파일러 옵션을 통해 C\+\+에 대한 모든 Microsoft 전용 확장을 사용하지 않도록 설정할 수 있습니다.  이 옵션은 여러 플랫폼에서 실행할 코드를 작성하려는 경우에 권장됩니다.  **\/Za** 컴파일러 옵션에 대한 자세한 내용은 [\/Za, \/Ze\(언어 확장 사용 안 함\)](../build/reference/za-ze-disable-language-extensions.md)를 참조하세요.  Visual C\+\+ 규칙에 대한 자세한 내용은 [Visual C\+\+에서 호환성 및 규격 문제](../misc/compatibility-and-compliance-issues-in-visual-cpp.md)를 참조하세요.  
  
## 미리 컴파일된 헤더  
 Microsoft C 및 C\+\+ 컴파일러는 인라인 코드를 포함하여 모든 C 또는 C\+\+ 코드를 미리 컴파일하는 옵션을 제공합니다.  이 성능 기능을 사용하여 안정적인 코드 본문을 컴파일하고, 코드의 컴파일된 상태를 파일에 저장하고, 후속 컴파일 중 미리 컴파일된 코드와 아직 개발 중인 코드를 결합할 수 있습니다.  안정적인 코드는 다시 컴파일할 필요가 없기 때문에 각 후속 컴파일 속도가 향상됩니다.  
  
 기본적으로 미리 컴파일된 코드는 **stdafx.h** 및 **stdafx.cpp** 파일에서 모두 지정됩니다.  **미리 컴파일된 헤더** 옵션을 선택 취소하지 않으면 **새 프로젝트** 마법사가 자동으로 이러한 파일을 만듭니다.  미리 컴파일된 헤더에 대한 자세한 내용은 [미리 컴파일된 헤더 파일 만들기](../build/reference/creating-precompiled-header-files.md)를 참조하세요.  
  
## 관련 단원  
 자세한 내용은 [UNIX에서 Win32로 이식](../porting/porting-from-unix-to-win32.md)을 참조하세요.  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)