---
title: "&lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 격리 COM | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.RegistrarScriptFile"
  - "VC.Project.VCManifestTool.ComponentFileName"
  - "VC.Project.VCManifestTool.TypeLibraryFile"
  - "VC.Project.VCManifestTool.ReplacementsFile"
dev_langs: 
  - "C++"
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 격리 COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 대화 상자를 사용하여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)에 대한 **격리 COM** 옵션을 지정할 수 있습니다.  
  
 이 속성 페이지 대화 상자에 액세스하려면 프로젝트에 대한 속성 페이지 또는 속성 시트를 엽니다.  **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음 **격리 COM**을 선택합니다.  
  
## 작업 목록  
  
-   [방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## UI 요소 목록  
 **형식 라이브러리 파일**  
 \/tlb 옵션을 사용하여 매니페스트 도구가 매니페스트 파일을 생성하는 데 사용할 형식 라이브러리 파일\(.tlb 파일\)의 이름을 지정합니다.  
  
 **등록자 스크립트 파일**  
 \/rgs 옵션을 사용하여 매니페스트 도구가 매니페스트 파일을 생성하는 데 사용할 등록자 스크립트 파일\(.rgs 파일\)의 이름을 지정합니다.  
  
 **구성 요소 파일 이름**  
 \/dll 옵션을 사용하여 매니페스트 도구가 생성할 리소스의 이름을 지정합니다.  **형식 라이브러리 파일** 또는 **등록자 스크립트 파일**에 대해 값을 지정한 경우 이 속성의 값을 입력해야 합니다.  
  
 **대체 파일**  
 \/replacements 옵션을 사용하여 .rgs 파일에 있는 대체 가능 문자열의 값이 들어 있는 파일에 대한 전체 경로를 지정합니다.  
  
## 참고 항목  
 [격리된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)   
 [Side\-by\-side 어셈블리](_win32_side_by_side_assemblies)   
 [ClickOnce 응용 프로그램 매니페스트](../Topic/ClickOnce%20Application%20Manifest.md)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)   
 [방법: 프로젝트 속성 시트 편집](../misc/how-to-edit-project-property-sheets.md)