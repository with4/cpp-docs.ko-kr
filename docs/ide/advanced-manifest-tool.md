---
title: 고급, 매니페스트 도구, 구성 속성, &lt;Projectname&gt; 속성 페이지 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47d4dc3ab325a7346d0e787a15d69d646896827d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326939"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>고급, 매니페스트 도구, 구성 속성, &lt;Projectname&gt; 속성 페이지 대화 상자
이 대화 상자를 사용하여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)에 대한 고급 옵션을 지정합니다.  
  
 이 속성 페이지 대화 상자에 액세스하려면 프로젝트 또는 속성 시트의 속성 페이지를 엽니다. **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음, **고급**을 선택합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **파일 해시 업데이트**  
 /hashupdate 옵션을 사용하여 매니페스트 도구가 `<file>` 요소에 지정된 파일의 해시를 계산한 다음, 계산된 값으로 해시 특성을 업데이트하도록 지정합니다.  
  
 **파일 해시 업데이트 검색 경로**  
 `<file>` 요소에서 참조되는 파일의 검색 경로를 지정합니다. 이 옵션은 /hashupdate 옵션도 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<file>요소](/visualstudio/deployment/file-element-clickonce-application)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)   