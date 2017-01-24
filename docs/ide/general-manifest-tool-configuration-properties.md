---
title: "&lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 일반 | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.MergeRulesFile"
  - "VC.Project.VCManifestTool.UseUnicodeResponseFiles"
  - "VC.Project.VCManifestTool.SuppressStartupBanner"
  - "VC.Project.VCManifestTool.UseFAT32Workaround"
  - "VC.Project.VCManifestTool.VerboseOutput"
  - "VC.Project.VCManifestTool.AssemblyIdentity"
dev_langs: 
  - "C++"
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 일반
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 대화 상자를 사용하여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)에 대한 일반 옵션을 지정할 수 있습니다.  
  
 이 속성 페이지 대화 상자에 액세스하려면 프로젝트에 대한 속성 페이지 또는 속성 시트를 엽니다.  **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음 **일반**을 선택합니다.  
  
## UI 요소 목록  
 **시작 배너 표시 안 함**  
 **예\(\/nologo\)**는 매니페스트 도구가 시작될 때 표준 Microsoft 저작권 데이터를 숨기도록 지정합니다.  mt.exe를 빌드 프로세스의 일부로 실행하거나 빌드 환경에서 실행할 때 로그 파일에 있는 원치 않는 출력이 표시되지 않도록 하려면 이 옵션을 사용합니다.  
  
 **자세한 정보 출력**  
 **예\(\/verbose\)**는 매니페스트를 생성하는 동안 추가 빌드 정보가 표시되도록 지정합니다.  
  
 **어셈블리 ID**  
 \/identity 옵션을 사용하여 [\<assemblyIdentity\> 요소](../Topic/%3CassemblyIdentity%3E%20Element%20\(ClickOnce%20Application\).md)에 대한 특성을 구성하는 ID 문자열을 지정합니다.  ID 문자열은 `name` 특성에 대한 값으로 시작되고 그 뒤에 *attribute* \= *value* 쌍이 나옵니다.  ID 문자열에서 특성은 쉼표로 구분됩니다.  
  
 다음은 ID 문자열의 예입니다.  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../Topic/ClickOnce%20Application%20Manifest.md)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)   
 [방법: 프로젝트 속성 시트 편집](../misc/how-to-edit-project-property-sheets.md)