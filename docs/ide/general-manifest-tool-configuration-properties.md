---
title: 매니페스트 도구 구성 속성 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
dev_langs:
- C++
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1953e7c37c07f66845510efe037015a537aa7baa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>일반, 매니페스트 도구, 구성 속성, &lt;Projectname&gt; 속성 페이지 대화 상자
일반 옵션을 지정 하려면이 대화 상자를 사용 하 여 [Mt.exe](http://msdn.microsoft.com/library/aa375649)합니다.  
  
 이 속성 페이지 대화 상자에 액세스 하려면 프로젝트 또는 속성 시트에 대 한 속성 페이지를 엽니다. 확장 된 **매니페스트 도구** 노드 아래의 **구성 속성**를 선택한 후 **일반**합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **시작 배너 표시 안 함**  
 **예 (/ nologo)** 매니페스트 도구가 시작 될 때 표준 Microsoft 저작권 데이터 숨겨집니다 있는지를 지정 합니다. Mt.exe 빌드 환경에서 또는 빌드 프로세스의 일부로 실행 하면 로그 파일에 원치 않는 출력을 표시 하지 않으려면이 옵션을 사용 합니다.  
  
 **자세한 정보를 출력**  
 **예 (/verbose)** 매니페스트를 생성 하는 동안 된 추가 빌드 정보가 표시 되도록 지정 합니다.  
  
 **어셈블리 Id**  
 /Identity 옵션을 사용 하 여 id 문자열을 지정에 대 한 특성을 구성 하는 [ \<y y > 요소](/visualstudio/deployment/assemblyidentity-element-clickonce-application)합니다. Id 문자열에 대 한 값으로 시작 된 `name` 특성을 선택한 다음 *특성* = *값* 쌍입니다. Id 문자열의 특성은 쉼표로 구분 됩니다.  
  
 다음은 id 문자열의 예입니다.  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)   
 [매니페스트 도구 속성 페이지](../ide/manifest-tool-property-pages.md)   
 [프로젝트 속성 사용](../ide/working-with-project-properties.md)   