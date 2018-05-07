---
title: 매니페스트 도구 입 / 출력 속성 (Visual c + +) | Microsoft Docs
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>입력 및 출력, 매니페스트 도구, 구성 속성, &lt;Projectname&gt; 속성 페이지 대화 상자
이 대화 상자를 사용 하 여 입력 및 출력 옵션을 지정 하려면 [Mt.exe](http://msdn.microsoft.com/library/aa375649)합니다.  
  
 이 속성 페이지 대화 상자에 액세스 하려면 프로젝트 또는 속성 시트에 대 한 속성 페이지를 엽니다. 확장 된 **매니페스트 도구** 노드 아래의 **구성 속성**를 선택한 후 **입력 및 출력**합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **추가 매니페스트 파일**  
 사용 하 여는 **/manifest** 병합 하거나 매니페스트 도구에서 처리 하는 추가 매니페스트 파일의 전체 경로 지정 하는 옵션입니다. 전체 경로 세미콜론으로 구분 됩니다.  
  
 **입력 리소스 매니페스트**  
 사용 하 여는 **/inputresource** 매니페스트 도구에 입력을 RT_MANIFEST 형식의 리소스의 전체 경로 지정 하는 옵션입니다. 경로 지정 된 리소스 ID가 올 수 있습니다. 예를 들어:  
  
 `dll_with_manifest.dll;#1`  
  
 리소스 ID는 선택 사항이 며 CREATEPROCESS_MANIFEST_RESOURCE_ID winuser.h에 기본적으로 합니다.  
  
 **매니페스트 포함**  
 **예** 프로젝트 시스템에서 어셈블리를 응용 프로그램 매니페스트 파일은 포함 하도록 지정 합니다.  
  
 **더** 프로젝트 시스템에서 독립 실행형 파일로 응용 프로그램 매니페스트 파일을 만들도록 지정 합니다.  
  
 **출력 매니페스트 파일**  
 출력 매니페스트 파일의 이름을 지정합니다. 이 속성은 매니페스트 파일은 하나만 작동 하는 매니페스트 도구 하는 경우 선택 사항입니다.  
  
 **매니페스트 리소스 파일**  
 리소스 파일이 프로젝트 출력에는 매니페스트를 포함 하는 데 사용 되는 출력을 지정 합니다.  
  
 **카탈로그 파일 생성**  
 사용 하 여는 **/makecdfs** 는 매니페스트 생성 됩니다. 카탈로그를 만드는 데 사용 되는 카탈로그 정의 파일 (.cdf 파일)을 지정 하는 옵션입니다.  
  
 **ManagedAssembly에서 매니페스트를 생성 합니다.**  
 관리 되는 어셈블리에서 매니페스트를 생성 합니다. (**-managedassemblyname: * * * 파일*).  
  
 **Dependency 요소를 표시 안 함**  
 함께 사용 된 **-managedassembly** 옵션입니다. 이 태그에는 최종 매니페스트에서 종속성 요소 생성이 되지 않습니다.  
  
 **Category 태그를 생성 합니다.**  
 함께 사용 된 **-managedassembly** 옵션입니다. 이 태그를 하면 범주 태그가 생성 됩니다.  
  
 **DPI 인식을 사용 하도록 설정**  
 DPI 인식 응용 프로그램 인지를 지정 합니다. 기본적으로 설정을 **예** MFC 프로젝트에 대 한 및 **아니요** MFC 프로젝트에만 기본적으로 DPI 인식 하기 때문에 다른 방법입니다. 에 대 한 설정을 재정의할 수 있습니다 **예** 서로 다른 DPI 설정 처리 하는 코드를 추가 하는 경우. 응용 프로그램은 유사 항목 일치 또는 작은으로 설정 하면 해당 DPI를 인식 하지 않을 때 나타날 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)   