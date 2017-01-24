---
title: "빌드 시스템 변경 사항 | Microsoft Docs"
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
  - "vc.msbuild.changes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드 시스템 변경 내용, $(Inherit)"
  - "빌드 시스템 변경 내용, $(NoInherit)"
  - "빌드 시스템 변경 내용, .vsprops"
  - "빌드 시스템 변경 내용, 사용자 지정 빌드 규칙"
  - "빌드 시스템 변경 내용, MSBuild"
  - "빌드 시스템 변경 내용, 프로젝트 파일(.vcxprog)"
  - "MSBuild, 빌드 시스템 변경 내용"
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 빌드 시스템 변경 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MSBuild는 Visual C\+\+ 프로젝트용 표준 빌드 시스템입니다.  그러나 Visual Studio 2008 및 이전 버전에서는 VCBuild 시스템 사용 되었습니다.  특정 파일 형식 및 VCBuild에 의존 하는 개념 없는 또는 현재 시스템에서 다르게 표현 됩니다.  이 문서에서는 현재 빌드 시스템의 차이점에 대해 설명합니다.  
  
## .vcproj가 이제 .vcxproj로 바뀜  
 프로젝트 파일에는 더 이상 .vcproj 파일 확장명이 사용되지 않습니다.  이전 버전의 Visual C\+\+에서 만든 프로젝트 파일은 현재 시스템에서 사용하는 형식으로 자동 변환됩니다.  프로젝트를 수동으로 업그레이드하는 방법에 대한 자세한 내용은 [\/Upgrade](../Topic/-Upgrade%20\(devenv.exe\).md)를 참조하십시오.  
  
 현재 버전에서 프로젝트 파일의 파일 확장명은 .vcxproj입니다.  
  
## .vsprops가 이제 .props로 바뀜  
 이전 버전에서 *프로젝트 속성 시트*는 파일 확장명이 .vsprops인 XML 기반 파일입니다.  프로젝트 속성 시트를 사용하여 컴파일러나 링커 같은 빌드 도구에 대한 스위치를 지정하고 사용자 정의 매크로를 만들 수 있습니다.  
  
 현재 버전에서 프로젝트 속성 시트의 파일 확장명은 .props입니다.  
  
## 사용자 지정 빌드 규칙 및 .rules 파일  
 이전 버전에서 *규칙 파일*은 파일 확장명이 .rules인 XML 기반 파일입니다.  규칙 파일을 사용하여 사용자 지정 빌드 규칙을 정의하고 이 규칙을 Visual C\+\+ 프로젝트의 빌드 프로세스로 통합할 수 있습니다.  하나 이상의 파일 확장명과 연결할 수 있는 사용자 지정 빌드 규칙을 사용하여 입력 파일을 도구로 전달할 수 있으며 그 결과 하나 이상의 출력 파일이 만들어집니다.  
  
 이번 릴리스에서는 사용자 지정 빌드 규칙이 .rules 파일이 아닌 .xml, .props 및 .targets의 세 가지 파일 형식으로 나타납니다.  이전 버전의 Visual C\+\+를 사용하여 만든 .rules 파일을 현재 버전으로 마이그레이션하면 동일한 .xml, .props 및 .targets이 만들어져 원래 .rules 파일과 함께 프로젝트에 저장됩니다.  
  
> [!IMPORTANT]
>  현재 릴리스에서 [!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)] 새 규칙의 생성을 지원 하지 않습니다.  이런 이유로 Visual C\+\+ 이전 버전을 사용 하 여 만든 프로젝트의 규칙 파일을 사용 하는 가장 쉬운 방법은 프로젝트를 현재 릴리스로 마이그레이션하는 것입니다.  
  
## 상속 매크로  
 이전 버전에서 **$\(Inherit\)** 매크로는 프로젝트 빌드 시스템에서 구성된 명령줄에 상속된 속성이 나타나는 순서를 지정합니다.  **$\(NoInherit\)** 매크로를 사용하면 모든 $\(Inherit\)가 무시되고 상속될 모든 속성이 상속되지 않습니다.  예를 들어 기본적으로 $\(Inherit\) 매크로를 사용하면 명령줄에 추가될 [\/I\(추가 포함 디렉터리\)](../build/reference/i-additional-include-directories.md) 컴파일러 옵션을 사용하여 파일이 지정됩니다.  
  
 현재 버전에서는 속성 값을 하나 이상의 리터럴 값 및 속성 매크로를 연결한 값으로 지정하여 상속이 지원됩니다.  **$\(Inherit\)** 및 **$\(NoInherit\)** 매크로는 지원되지 않습니다.  
  
 다음 예제에서는 속성 페이지의 속성에 세미콜론으로 구분된 목록이 할당됩니다.  목록은 *\<value\>* 리터럴과 **$\(***MyProperty***\)** 매크로 표기법을 사용하여 액세스되는 `MyProperty` 속성 값을 연결한 값으로 구성됩니다.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## .vcxproj.user 파일  
 사용자 파일\(.vcxproj.user\)에는 디버깅 및 배포 설정과 같은 사용자별 속성이 저장됩니다.  vcxproj.user 파일은 특정 사용자의 모든 프로젝트에 적용됩니다.  
  
## .vcxproj.filters 파일  
 **솔루션 탐색기**를 사용하여 프로젝트에 파일을 추가하면 필터 파일\(.vcxproj.filters\)이 파일 확장명에 따라 **솔루션 탐색기** 트리 뷰에서 파일이 추가되는 위치를 정의합니다.  
  
## VC\+\+ 디렉터리 설정  
 Visual C\+\+ 디렉터리 설정은 [VC\+\+ 디렉터리 속성 페이지](../ide/vcpp-directories-property-page.md)에서 지정합니다.  이전 버전의 Visual Studio에서는 디렉터리 설정이 사용자별로 적용되고 sysincl.dat 파일에 제외되는 디렉터리 목록을 지정했습니다.  
  
 명령줄에서 [devenv \/resetsettings](../Topic/-ResetSettings%20\(devenv.exe\).md)를 실행하는 경우 VC\+\+ 디렉터리 설정을 변경할 수 없습니다.  **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택한 후 **모든 설정 다시 설정**을 선택하는 경우에도 설정을 변경할 수 없습니다.  
  
 이전 버전의 Visual C\+\+에서 만든 .vssettings 파일에서 VC\+\+ 디렉터리 설정을 마이그레이션합니다.  **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 클릭하고 **선택한 환경 설정 가져오기**를 선택한 다음 마법사의 지시에 따릅니다.  또는 Visual Studio를 처음 시작할 때 **기본 환경 설정 선택** 대화 상자에서 **이전 버전의 사용할 수 있는 설정을 마이그레이션한 다음 아래 선택된 기본 설정과 함께 적용합니다.**를 선택합니다.  
  
## 참고 항목  
 [MSBuild\(Visual C\+\+\)](../build/msbuild-visual-cpp.md)