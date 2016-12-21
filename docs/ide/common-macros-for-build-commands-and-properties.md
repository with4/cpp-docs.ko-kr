---
title: "빌드 명령 및 속성 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles"
  - "VC.Project.VCCLCompilerTool.XMLDocumentationFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "$(ConfigurationName) 매크로"
  - "$(DevEnvDir) 매크로"
  - "$(FrameworkDir) 매크로"
  - "$(FrameworkSDKDir) 매크로"
  - "$(FrameworkVersion) 매크로"
  - "$(FxCopDir) 매크로"
  - "$(Inherit) 매크로"
  - "$(InputDir) 매크로"
  - "$(InputExt) 매크로"
  - "$(InputFileName) 매크로"
  - "$(InputName) 매크로"
  - "$(InputPath) 매크로"
  - "$(IntDir) 매크로"
  - "$(NoInherit) 매크로"
  - "$(OutDir) 매크로"
  - "$(ParentName) 매크로"
  - "$(PlatformName) 매크로"
  - "$(ProjectDir) 매크로"
  - "$(ProjectExt) 매크로"
  - "$(ProjectFileName) 매크로"
  - "$(ProjectName) 매크로"
  - "$(ProjectPath) 매크로"
  - "$(References) 매크로"
  - "$(RemoteMachine) 매크로"
  - "$(RootNamespace) 매크로"
  - "$(SafeRootNamespace) 매크로"
  - "$(SolutionDir) 매크로"
  - "$(SolutionExt) 매크로"
  - "$(SolutionFileName) 매크로"
  - "$(SolutionName) 매크로"
  - "$(SolutionPath) 매크로"
  - "$(StopEvaluating) 매크로"
  - "$(TargetDir) 매크로"
  - "$(TargetExt) 매크로"
  - "$(TargetFileName) 매크로"
  - "$(TargetName) 매크로"
  - "$(TargetPath) 매크로"
  - "$(VCInstallDir) 매크로"
  - "$(VSInstallDir) 매크로"
  - "$(WebDeployPath) 매크로"
  - "$(WebDeployRoot) 매크로"
  - "빌드 매크로[C++]"
  - "빌드[C++], 매크로"
  - "ConfigurationName 매크로 $(ConfigurationName)"
  - "DevEnvDir 매크로 $(DevEnvDir)"
  - "FrameworkDir 매크로 $(FrameworkDir)"
  - "FrameworkSDKDir 매크로 $(FrameworkSDKDir)"
  - "FrameworkVersion 매크로 $(FrameworkVersion)"
  - "FxCopDir 매크로 $(FxCopDir)"
  - "Inherit 매크로 $(Inherit)"
  - "InputDir 매크로 $(InputDir)"
  - "InputExt 매크로 $(InputExt)"
  - "InputFileName 매크로 $(InputFileName)"
  - "InputName 매크로 $(InputName)"
  - "InputPath 매크로 $(InputPath)"
  - "IntDir 매크로 $(IntDir)"
  - "매크로[C++], 빌드 매크로"
  - "NoInherit 매크로 $(NoInherit)"
  - "OutDir 매크로 $(OutDir)"
  - "ParentName 매크로 $(ParentName)"
  - "PlatformName 매크로 $(PlatformName)"
  - "ProjectDir 매크로 $(ProjectDir)"
  - "ProjectExt 매크로 $(ProjectExt)"
  - "ProjectFileName 매크로 $(ProjectFileName)"
  - "ProjectName 매크로 $(ProjectName)"
  - "ProjectPath 매크로 $(ProjectPath)"
  - "속성[C++], 빌드 속성 매크로"
  - "References 매크로 $(References)"
  - "RemoteMachine 매크로 $(RemoteMachine)"
  - "RootNamespace 매크로 $(RootNamespace)"
  - "SafeRootNamespace 매크로 $(SafeRootNamespace)"
  - "SolutionDir 매크로 $(SolutionDir)"
  - "SolutionExt 매크로 $(SolutionExt)"
  - "SolutionFileName 매크로 $(SolutionFileName)"
  - "SolutionName 매크로 $(SolutionName)"
  - "SolutionPath 매크로 $(SolutionPath)"
  - "StopEvaluating 매크로 $(StopEvaluating)"
  - "TargetDir 매크로 $(TargetDir)"
  - "TargetExt 매크로 $(TargetExt)"
  - "TargetFileName 매크로 $(TargetFileName)"
  - "TargetName 매크로 $(TargetName)"
  - "TargetPath 매크로 $(TargetPath)"
  - "VCInstallDir 매크로 $(VCInstallDir)"
  - "VSInstallDir 매크로 $(VSInstallDir)"
  - "WebDeployPath 매크로 $(WebDeployPath)"
  - "WebDeployRoot 매크로 $(WebDeployRoot)"
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
caps.latest.revision: 22
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 빌드 명령 및 속성 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트의 **속성 페이지** 대화 상자에서 문자열이 허용되는 모든 위치에서 이러한 매크로를 사용할 수 있습니다. 이러한 매크로는 대\/소문자를 구분하지 않습니다.  
  
 현재 사용 가능한 매크로를 표시하려면 속성 이름의 오른쪽에 있는 열에서 드롭다운 화살표를 클릭합니다.**편집**을 사용할 수 있으면 클릭한 다음 편집 대화 상자에서 **매크로**를 클릭합니다. 자세한 내용은 [속성 페이지](../ide/property-pages-visual-cpp.md)의 **Specifying User\-Defined Values** 단원을 참조하세요.  
  
 "사용되지 않음"으로 표시된 매크로는 더 이상 사용되지 않거나 해당 [항목 메타데이터 매크로](../Topic/ItemMetadata%20Element%20\(MSBuild\).md)\(**%\(***name***\)**\)로 바뀌었습니다. "사용되지 않음, 마이그레이션됨"으로 표시된 매크로도 더 이상 사용되지 않습니다. 또한 매크로를 포함하는 프로젝트가 Visual Studio 2008에서 마이그레이션된 경우 Visual Studio는 매크로를 해당하는 현재 매크로로 변환합니다.  
  
|매크로|설명|  
|---------|--------|  
|**$\(RemoteMachine\)**|디버그 속성 페이지에서 **Remote Machine** 속성의 값으로 설정합니다. 자세한 내용은 [C\/C\+\+ 디버그 구성에 대한 프로젝트 설정 변경](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md)을 참조하세요.|  
|**$\(Configuration\)**|현재 프로젝트 구성의 이름\(예: "Debug"\)입니다.|  
|**$\(Platform\)**|현재 프로젝트 플랫폼의 이름\(예: "Win32"\)입니다.|  
|**$\(ParentName\)**|\(사용되지 않음\) 이 프로젝트 항목을 포함하는 항목의 이름입니다. 부모 폴더 이름 또는 프로젝트 이름이 됩니다.|  
|**$\(RootNameSpace\)**|응용 프로그램을 포함하는 네임스페이스\(있는 경우\)입니다.|  
|**$\(IntDir\)**|중간 파일에 대해 지정된 디렉터리 경로입니다. 상대 경로인 경우 중간 파일은 프로젝트 디렉터리에 추가된 이 경로로 이동합니다. 이 경로의 끝에는 슬래시가 있어야 합니다.**Intermediate Directory** 속성에 대한 값으로 확인됩니다.**$\(OutDir\)**을 사용하여 이 속성을 정의할 수 없습니다.|  
|**$\(OutDir\)**|출력 파일 디렉터리에 대한 경로입니다. 상대 경로인 경우 출력 파일은 프로젝트 디렉터리에 추가된 이 경로로 이동합니다. 이 경로의 끝에는 슬래시가 있어야 합니다.**Output Directory** 속성에 대한 값으로 확인됩니다.**$\(IntDir\)**을 사용하여 이 속성을 정의할 수 없습니다.|  
|**$\(DevEnvDir\)**|Visual Studio의 설치 디렉터리\(드라이브 \+ 경로로 정의됨\)이며, 뒤의 백슬래시 '\\'를 포함합니다.|  
|**$\(InputDir\)**|\(사용되지 않음, 마이그레이션됨\) 입력 파일의 디렉터리\(드라이브 \+ 경로로 정의됨\)이며, 뒤에 백슬래시 '\\'가 포함됩니다. 프로젝트가 입력인 경우 이 매크로는 **$\(ProjectDir\)**에 해당합니다.|  
|**$\(InputPath\)**|\(사용되지 않음, 마이그레이션됨\) 입력 파일의 절대 경로 이름\(드라이브 \+ 경로 \+ 기본 이름 \+ 파일 확장명으로 정의됨\)입니다. 프로젝트가 입력인 경우 이 매크로는 **$\(ProjectPath\)**에 해당합니다.|  
|**$\(InputName\)**|\(사용되지 않음, 마이그레이션됨\) 입력 파일의 기본 이름입니다. 프로젝트가 입력인 경우 이 매크로는 **$\(ProjectName\)**에 해당합니다.|  
|**$\(InputFileName\)**|\(사용되지 않음, 마이그레이션됨\) 입력 파일의 파일 이름\(기본 이름 \+ 파일 확장명으로 정의됨\)입니다. 프로젝트가 입력인 경우 이 매크로는 **$\(ProjectFileName\)**에 해당합니다.|  
|**$\(InputExt\)**|\(사용되지 않음, 마이그레이션됨\) 입력 파일의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다. 프로젝트가 입력인 경우 이 매크로는 **$\(ProjectExt\)**에 해당합니다.|  
|**$\(ProjectDir\)**|프로젝트의 디렉터리\(드라이브 \+ 경로로 정의됨\)이며, 뒤의 백슬래시 '\\'를 포함합니다.|  
|**$\(ProjectPath\)**|프로젝트의 절대 경로 이름\(드라이브 \+ 경로 \+ 기본 이름 \+ 파일 확장명으로 정의됨\)입니다.|  
|**$\(ProjectName\)**|프로젝트의 기본 이름입니다.|  
|**$\(ProjectFileName\)**|프로젝트의 파일 이름\(기본 이름 \+ 파일 확장명으로 정의됨\)입니다.|  
|**$\(ProjectExt\)**|프로젝트의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다.|  
|**$\(SolutionDir\)**|솔루션의 디렉터리\(드라이브 \+ 경로로 정의됨\)이며, 뒤의 백슬래시 '\\'를 포함합니다.|  
|**$\(SolutionPath\)**|솔루션의 절대 경로 이름\(드라이브 \+ 경로 \+ 기본 이름 \+ 파일 확장명으로 정의됨\)입니다.|  
|**$\(SolutionName\)**|솔루션의 기본 이름입니다.|  
|**$\(SolutionFileName\)**|솔루션의 파일 이름\(기본 이름 \+ 파일 확장명으로 정의됨\)입니다.|  
|**$\(SolutionExt\)**|솔루션의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다.|  
|**$\(TargetDir\)**|빌드에 대한 기본 출력 파일의 디렉터리\(드라이브 \+ 경로로 정의됨\)이며, 뒤에 백슬래시 '\\'가 포함됩니다.|  
|**$\(TargetPath\)**|빌드에 대한 기본 출력 파일의 절대 경로 이름\(드라이브 \+ 경로 \+ 기본 이름 \+ 파일 확장명으로 정의됨\)입니다.|  
|**$\(TargetName\)**|빌드에 대한 기본 출력 파일의 기본 이름입니다.|  
|**$\(TargetFileName\)**|빌드에 대한 기본 출력 파일의 파일 이름\(기본이름 \+ 파일 확장명으로 정의됨\)입니다.|  
|**$\(TargetExt\)**|빌드에 대한 기본 출력 파일의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다.|  
|**$\(VSInstallDir\)**|Visual Studio을 설치한 디렉터리입니다.<br /><br /> 이 속성에는 대상 Visual Studio의 버전이 포함되며, 이 버전은 호스트 Visual Studio와 다를 수 있습니다. 예를 들어 `$(PlatformToolset) = v110`으로 빌드하는 경우 **$\(VSInstallDir\)**에는 Visual Studio 2012 설치 경로가 포함됩니다.|  
|**$\(VCInstallDir\)**|Visual C\+\+를 설치한 디렉터리입니다.<br /><br /> 이 속성에는 대상 Visual C\+\+의 버전이 포함되며, 이 버전은 호스트 Visual Studio와 다를 수 있습니다. 예를 들어 `$(PlatformToolset) = v90`으로 빌드하는 경우 **$\(VCInstallDir\)**에는 Visual C\+\+ 2008 설치 경로가 포함됩니다.|  
|**$\(FrameworkDir\)**|.NET Framework가 설치된 디렉터리입니다.|  
|**$\(FrameworkVersion\)**|Visual Studio에서 사용하는 .NET Framework의 버전입니다.**$\(FrameworkDir\)**과 함께 사용할 경우 Visual Studio에서 사용하는 .NET Framework 버전의 전체 경로입니다.|  
|**$\(FrameworkSDKDir\)**|.NET Framework를 설치한 디렉터리입니다. .NET Framework는 Visual Studio의 일부로 설치하거나 별도로 설치할 수 있습니다.|  
|**$\(WebDeployPath\)**|웹 배포 루트에서 프로젝트 출력이 속하는 상대 경로입니다.<xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>와 동일한 값을 반환합니다.|  
|**$\(WebDeployRoot\)**|**\<localhost\>** 위치의 절대 경로입니다. 예를 들어 c:\\inetpub\\wwwroot입니다.|  
|**$\(SafeParentName\)**|\(사용되지 않음\) 유효한 이름 형식인 직계 부모의 이름입니다. 예를 들어 양식은 .resx 파일의 부모입니다.|  
|**$\(SafeInputName\)**|\(사용되지 않음\) 파일 확장명을 뺀 유효한 클래스 이름으로 파일의 이름입니다.|  
|**$\(SafeRootNamespace\)**|\(사용되지 않음\) 프로젝트 마법사에서 코드를 추가할 네임스페이스 이름입니다. 이 네임스페이스 이름에는 유효한 C\+\+ 식별자에 사용할 수 있는 문자만 포함됩니다.|  
|**$\(FxCopDir\)**|fxcop.cmd 파일의 경로입니다. fxcop.cmd 파일은 일부 Visual C\+\+ 버전에서 설치되지 않습니다.|  
  
## 참고 항목  
 [Visual Studio에서 C\+\+ 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)