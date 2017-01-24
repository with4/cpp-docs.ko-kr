---
title: "명령줄 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드[C++], 명령줄"
  - "명령줄[C++], 빌드"
  - "명령줄[C++], 컴파일러"
  - "명령줄 빌드[C++]"
  - "소스 코드 컴파일[C++], 명령줄"
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 명령줄 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 포함된 도구를 사용하여 명령줄에서 C 및 C\+\+ 응용 프로그램을 빌드할 수 있습니다.  모든 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전은 컴파일러, 링커 및 기타 빌드 도구가 포함된 명령줄 도구 집합과 필수 빌드 환경을 설정하는 명령 파일을 설치합니다.  기본적으로 이러한 도구는 *드라이브*:\\Program Files \(x86\)\\Microsoft Visual Studio *버전*\\VC\\bin\\에 설치됩니다.  컴퓨터의 실제 디렉터리는 시스템, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전 및 설치 선택 사항에 따라 달라집니다.  
  
 제대로 작업하려면 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 명령줄 도구에는 설치에 맞춰 사용자 지정된 여러 환경 변수가 필요합니다.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]가 설치되면 Visual Studio는 필수 환경 변수를 설정하기 위해 실행할 수 있는 vcvarsall.bat 명령 파일을 만듭니다.  또한 이러한 변수가 이미 설정되어 있는 개발자 명령 프롬프트 창을 시작하는 바로 가기도 만듭니다.  이러한 환경 변수는 사용자의 설치에 고유하게 설정되며 제품 업데이트 또는 업그레이드 시 변경될 수 있습니다.  따라서 이러한 변수를 직접 설정하기 보다는 vcvarsall.bat 또는 개발자 명령 프롬프트 바로 가기를 사용하는 것이 좋습니다.  자세한 내용은 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하십시오.  
  
### 개발자 명령 프롬프트 창을 열려면  
  
1.  Windows 8 시작 화면에서 Visual Studio Tools를 입력합니다.  입력한 내용에 따라 검색 결과가 바뀝니다. **Visual Studio Tools**가 나타나면 선택합니다.  
  
     이전 버전의 Windows에는 **시작**을 선택한 다음 검색 상자에 Visual Studio Tools를 입력합니다.  검색 결과에 **Visual Studio Tools**가 나타나면 선택합니다.  
  
2.  **Visual Studio Tools** 폴더에서 사용 중인 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전에 해당하는 **개발자 명령 프롬프트**를 엽니다.  
  
 명령줄에서 C\/C\+\+ 프로젝트를 빌드하려면 다음 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 명령줄 도구를 사용할 수 있습니다.  
  
 [CL](../build/reference/compiling-a-c-cpp-program.md)  
 컴파일러\(cl.exe\)를 사용하여 소스 코드 파일을 컴파일한 다음 앱, 라이브러리 및 DLL에 연결합니다.  
  
 [링크](../build/reference/linking.md)  
 링커\(link.exe\)를 사용하여 컴파일된 개체 파일 및 라이브러리를 앱 및 DLL에 연결합니다.  
  
 [MSBuild\(Visual C\+\+\)](../build/msbuild-visual-cpp.md)  
 MSBuild\(msbuild.exe\)를 사용하여 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 프로젝트 및 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 솔루션을 빌드합니다.  이는 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE에서 프로젝트 **빌드** 또는 **솔루션 빌드** 명령을 실행하는 것과 같습니다.  
  
 [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md)  
 명령줄 스위치\(예: **\/Build** 또는 **\/Clean**\)와 함께 DEVENV\(devenv.exe\)를 사용하여 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE를 표시하지 않고 특정 빌드 명령을 수행합니다.  
  
 [NMAKE](../build/nmake-reference.md)  
 NMAKE\(nmake.exe\)를 사용하여 기존 메이크파일로 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 프로젝트 빌드 작업을 자동화합니다.  
  
 명령줄에서 빌드하는 경우 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]를 시작한 다음 메뉴 모음에서 **도움말**, **검색**을 선택하여 경고, 오류 및 메시지에 대한 정보를 얻을 수 있습니다.  
  
## 단원 내용  
 설명서의 이 섹션에 있는 문서는 명령줄에서 앱을 빌드하는 방법을 보여주고, 64비트 도구 집합을 사용하고 x86, x64 및 ARM 플랫폼을 대상으로 하도록 명령줄 빌드 환경을 사용자 지정하는 방법에 대해 설명하고, 명령줄 빌드 도구인 MSBuild 및 NMAKE를 사용하는 방법을 보여줍니다.  
  
 [연습: 명령줄에서 네이티브 C\+\+ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
 명령줄에서 간단한 C\+\+ 프로그램을 만들고 컴파일하는 방법을 보여주는 예제를 제공합니다.  
  
 [연습: 명령줄에서 C 프로그램 컴파일](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
 C 프로그래밍 언어로 작성한 프로그램을 컴파일하는 방법에 대해 설명합니다.  
  
 [연습: 명령줄에서 C\+\+\/CLI 프로그램 컴파일](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
 .NET Framework를 사용하는 C\+\+\/CLI 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.  
  
 [연습: 명령줄에서 C\+\+\/CX 프로그램 컴파일](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
 Windows 런타임을 사용하는 C\+\+\/CX 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.  
  
 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
 32비트 또는 64비트 도구 집합을 사용하여 x86, x64 및 ARM 플랫폼을 대상으로 하는 명령줄 빌드에 필요한 환경 변수가 들어있는 명령 프롬프트 창을 시작하는 방법에 대해 설명합니다.  
  
 [NMAKE 참조](../build/nmake-reference.md)  
 Microsoft Program Maintenance Utility\(NMAKE.EXE\)에 대해 설명하는 문서의 링크를 제공합니다.  
  
 [MSBuild\(Visual C\+\+\)](../build/msbuild-visual-cpp.md)  
 MSBuild.EXE를 사용하는 방법에 대해 설명하는 문서의 링크를 제공합니다.  
  
## 관련 단원  
 [\/MD, \/MT, \/LD\(런타임 라이브러리 사용\)](../build/reference/md-mt-ld-use-run-time-library.md)  
 컴파일러 옵션을 사용하여 디버그 또는 릴리스 런타임 라이브러리를 사용하는 방법에 대해 설명합니다.  
  
 [C\/C\+\+ 컴파일러 옵션](../build/reference/compiler-options.md)  
 C 및 C\+\+ 컴파일러 옵션과 CL.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.  
  
 [링커 옵션](../build/reference/linker-options.md)  
 링커 옵션 및 LINK.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.  
  
 [C\/C\+\+ 빌드 도구](../build/reference/c-cpp-build-tools.md)  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에 포함된 C\/C\+\+ 빌드 도구에 대한 링크를 제공합니다.  
  
## 참고 항목  
 [C\/C\+\+ 프로그램 빌드](../build/building-c-cpp-programs.md)