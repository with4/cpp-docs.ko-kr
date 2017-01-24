---
title: "&lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 입력 및 출력 | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.OutputManifestFile"
  - "VC.Project.VCManifestTool.InputResourceManifests"
  - "VC.Project.VCManifestTool.EmbedManifest"
  - "VC.Project.VCManifestTool.AdditionalManifestFiles"
  - "VC.Project.VCManifestTool.DependencyInformationFile"
  - "VC.Project.VCManifestTool.OutputResourceManifest"
  - "VC.Project.VCManifestTool.GenerateCatalogFiles"
dev_langs: 
  - "C++"
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 입력 및 출력
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 대화 상자를 사용하여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)에 대한 입력 및 출력 옵션을 지정할 수 있습니다.  
  
 이 속성 페이지 대화 상자에 액세스하려면 프로젝트에 대한 속성 페이지 또는 속성 시트를 엽니다.  **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음 **입력 및 출력**을 선택합니다.  
  
## UI 요소 목록  
 **추가 매니페스트 파일**  
 **\/manifest** 옵션을 사용하여 매니페스트 도구가 처리하거나 병합할 추가 매니페스트 파일의 전체 경로를 지정합니다.  전체 경로는 세미콜론으로 구분됩니다.  
  
 **입력 리소스 매니페스트**  
 **\/inputresource** 옵션을 사용하여 매니페스트 도구에 입력할 RT\_MANIFEST 형식 리소스의 전체 경로를 지정합니다.  경로 뒤에 지정된 리소스 ID가 나올 수 있습니다.  예를 들면 다음과 같습니다.  
  
 `dll_with_manifest.dll;#1`  
  
 리소스 ID는 선택적이며 기본값은 winuser.h의 CREATEPROCESS\_MANIFEST\_RESOURCE\_ID입니다.  
  
 **매니페스트 포함**  
 **예**는 프로젝트 시스템이 응용 프로그램 매니페스트 파일을 어셈블리에 포함하도록 지정합니다.  
  
 **아니요**는 프로젝트 시스템이 응용 프로그램 매니페스트 파일을 독립 실행형 파일로 만들도록 지정합니다.  
  
 **출력 매니페스트 파일**  
 출력 매니페스트 파일의 이름을 지정합니다.  매니페스트 도구가 하나의 매니페스트 파일에서만 작동하는 경우 이 속성은 선택적입니다.  
  
 **매니페스트 리소스 파일**  
 프로젝트 출력에 매니페스트를 포함하는 데 사용한 출력 리소스 파일을 지정합니다.  
  
 **카탈로그 파일 생성**  
 **\/makecdfs** 옵션을 사용하여 매니페스트 도구가 카탈로그를 만드는 데 사용되는 카탈로그 정의 파일\(.cdf 파일\)을 생성하도록 지정합니다.  
  
 **ManagedAssembly에서 매니페스트 생성**  
 관리되는 어셈블리에서 매니페스트를 생성합니다.  \(**\-managedassemblyname:***파일*\).  
  
 **Dependency 요소 표시 안 함**  
 **\-managedassembly** 옵션과 함께 사용합니다.  이 태그는 최종 매니페스트 종속성 요소의 생성을 표시하지 않습니다.  
  
 **범주 태그 생성**  
 **\-managedassembly** 옵션과 함께 사용합니다.  이 태그는 범주 태그가 생성되도록 합니다.  
  
 **DPI 인식 사용**  
 응용 프로그램이 DPI를 인식하는지 여부를 지정합니다.  기본적으로 설정은 MFC 프로젝트만이 DPI 인식을 빌드했기 때문에 MFC 프로젝트의 경우 **Yes**이고 그렇지 않으면 **No**입니다.  다른 DPI 설정을 처리하는 코드를 추가하는 경우 설정을 **예**로 재정의할 수 있습니다.  DPI 인식이 되지 않을 때 DPI 인식으로 설정할 경우 응용 프로그램이 유사하거나 작게 나타날 수 있습니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../Topic/ClickOnce%20Application%20Manifest.md)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)   
 [방법: 프로젝트 속성 시트 편집](../misc/how-to-edit-project-property-sheets.md)