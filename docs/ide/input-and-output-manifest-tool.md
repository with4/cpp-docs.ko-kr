---
title: 매니페스트 도구 입력 및 출력 속성(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs:
- C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15be7636188bb670febd7875974d683c1d78360f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33331560"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>입력 및 출력, 매니페스트 도구, 구성 속성, &lt;Projectname&gt; 속성 페이지 대화 상자
이 대화 상자를 사용하여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)에 대한 입력 및 출력 옵션을 지정합니다.  
  
 이 속성 페이지 대화 상자에 액세스하려면 프로젝트 또는 속성 시트의 속성 페이지를 엽니다. **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음, **입력 및 출력**을 선택합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **추가 매니페스트 파일**  
 **/manifest** 옵션을 사용하여 매니페스트 도구가 처리하거나 병합할 추가 매니페스트 파일의 전체 경로를 지정합니다. 전체 경로는 세미콜론으로 구분됩니다.  
  
 **입력 리소스 매니페스트**  
 **/inputresource** 옵션을 사용하여 매니페스트 도구에 입력할 RT_MANIFEST 형식의 리소스 전체 경로를 지정합니다. 경로 다음에 지정된 리소스 ID가 올 수 있습니다. 예:  
  
 `dll_with_manifest.dll;#1`  
  
 리소스 ID는 선택 사항이며 기본적으로 winuser.h에서 CREATEPROCESS_MANIFEST_RESOURCE_ID로 설정됩니다.  
  
 **매니페스트 포함**  
 **예**는 프로젝트 시스템이 응용 프로그램 매니페스트 파일을 어셈블리에 포함하도록 지정합니다.  
  
 **아니요**는 프로젝트 시스템이 응용 프로그램 매니페스트 파일을 독립형 파일로 생성하도록 지정합니다.  
  
 **출력 매니페스트 파일**  
 출력 매니페스트 파일의 이름을 지정합니다. 이 속성은 매니페스트 도구에서 하나의 매니페스트 파일만 작동하는 경우 선택 사항입니다.  
  
 **매니페스트 리소스 파일**  
 매니페스트를 프로젝트 출력에 포함시키는 데 사용되는 출력 리소스 파일을 지정합니다.  
  
 **카탈로그 파일 생성**  
 **/makecdfs** 옵션을 사용하여 매니페스트 도구가 카탈로그를 만드는 데 사용되는 카탈로그 정의 파일(.cdf 파일)을 생성하도록 지정합니다.  
  
 **ManagedAssembly에서 매니페스트 생성**  
 관리되는 어셈블리에서 매니페스트를 생성합니다. (**-managedassemblyname:***file*).  
  
 **종속성 요소 억제**  
 **-managedassembly** 옵션과 함께 사용됩니다. 이 태그는 최종 매니페스트에서 종속성 요소의 생성을 억제합니다.  
  
 **범주 태그 생성**  
 **-managedassembly** 옵션과 함께 사용됩니다. 이 태그는 범주 태그를 생성합니다.  
  
 **DPI 인식 활성화**  
 응용 프로그램이 DPI를 인식하는지 여부를 지정합니다. 기본적으로 MFC 프로젝트는 **예**로 설정되고, 다른 프로젝트는 **아니요**로 설정됩니다. MFC 프로젝트에만 DPI 인식 기능이 내장되어 있기 때문입니다. 다른 DPI 설정을 처리하는 코드를 추가하는 경우, 이 설정을 **예**로 재정의할 수 있습니다. 응용 프로그램이 DPI를 인식하지 않는데 인식하는 것으로 설정할 경우 응용 프로그램이 흐릿하게 또는 작게 표시될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)   