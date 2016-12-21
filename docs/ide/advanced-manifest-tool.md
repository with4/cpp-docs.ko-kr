---
title: "&lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 고급 | Microsoft Docs"
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
  - "VC.Project.VCManifestTool.KeyFile"
  - "VC.Project.VCManifestTool.UpdateFileHashes"
  - "VC.Project.VCManifestTool.UpdateFileHashesSearchPath"
  - "VC.Project.VCManifestTool.ValidateSignature"
  - "VC.Project.VCManifestTool.KeyContainer"
dev_langs: 
  - "C++"
ms.assetid: 3d587366-05ea-4956-a978-313069660735
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;Projectname&gt; 속성 페이지 대화 상자, 구성 속성, 매니페스트 도구, 고급
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 대화 상자를 사용하여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)에 대한 고급 옵션을 지정할 수 있습니다.  
  
 이 속성 페이지 대화 상자에 액세스하려면 프로젝트에 대한 속성 페이지 또는 속성 시트를 엽니다.  **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음 **고급**을 선택합니다.  
  
## UI 요소 목록  
 **파일 해시 업데이트**  
 \/hashupdate 옵션을 사용하면 매니페스트 도구가 `<file>` 요소에 지정된 파일의 해시를 계산한 다음 계산된 값을 사용하여 해시 특성을 업데이트하도록 지정됩니다.  
  
 **파일 해시 업데이트 검색 경로**  
 `<file>` 요소에서 참조되는 파일에 대한 검색 경로를 지정합니다.  이 옵션은 또한 \/hashupdate 옵션도 사용합니다.  
  
## 참고 항목  
 [\<file\> 요소](../Topic/%3Cfile%3E%20Element%20\(ClickOnce%20Application\).md)   
 [ClickOnce 응용 프로그램 매니페스트](../Topic/ClickOnce%20Application%20Manifest.md)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)   
 [방법: 프로젝트 속성 시트 편집](../misc/how-to-edit-project-property-sheets.md)