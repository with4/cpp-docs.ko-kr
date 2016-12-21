---
title: "링커 속성 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RegisterOutput"
  - "VC.Project.VCLinkerTool.IgnoreImportLibrary"
  - "VC.Project.VCLinkerTool.UseLibraryDependencyInputs"
  - "VC.Project.VCLinkerTool.LinkLibraryDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자별 리디렉션"
  - "링커 속성 페이지"
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 링커 속성 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 **일반** 링커 속성 페이지의 다음 속성에 대해 설명합니다.  
  
 **가져오기 라이브러리 무시**  
 이 빌드에서 생성된 모든 .lib 출력을 종속 프로젝트에 링크하지 않도록 링커에 지시합니다.  이를 통해 프로젝트 시스템에서는 빌드할 때 .lib 파일을 생성하지 않는 .dll 파일을 처리할 수 있습니다.  프로젝트가 DLL을 생성하는 다른 프로젝트에 종속된 경우 프로젝트 시스템에서는 해당 자식 프로젝트에서 생성한 .lib 파일을 자동으로 링크합니다.  이러한 기능은 COM DLL이나 리소스 전용 DLL을 생성하는 프로젝트에는 필요하지 않습니다. 이 DLL에는 내용을 알려주는 의미 있는 내보내기가 없습니다.  DLL에 이러한 내보내기가 없으면 링커는 .lib 파일을 생성하지 않습니다.  내보내기 .lib 파일이 디스크에 없고 프로젝트 시스템에서 이러한 누락된 DLL에 링크하도록 링커에 지시할 경우 링크는 실패합니다.  
  
 **가져오기 라이브러리 무시**를 사용하여 이 문제를 해결하십시오.  이 옵션을 `Yes`로 설정하면 프로젝트 시스템에서는 해당 .lib 파일의 존재 여부를 무시하며 이 프로젝트에 종속된 모든 프로젝트가 존재하지 않는 .lib 파일에 링크되지 않도록 합니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>를 참조하십시오.  
  
 **출력 등록**  
 .dll 프로젝트에만 유효한 regsvr32.exe \/s $\(TargetPath\)를 실행합니다.  .exe 프로젝트의 경우에는 이 속성은 무시됩니다.  .exe 출력을 등록하면 등록된 .exe 파일에 항상 필요한 사용자 지정 등록을 수행하도록 구성에 대해 빌드 후 이벤트를 설정합니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>을 참조하십시오.  
  
 **사용자별 리디렉션**  
 기존의 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]는 HKEY\_CLASSES\_ROOT\(HKCR\)에 등록됩니다.  [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]에서 HKCR에 액세스하려면 관리자 모드로 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]를 실행해야 합니다.  개발자는 항상 관리자 모드로 실행할 필요는 없지만 등록 작업 시에는 관리자 모드로 실행해야 합니다.  사용자별 리디렉션을 사용하면 이 모드로 실행할 필요 없이 등록할 수 있습니다.  
  
 사용자별 리디렉션을 사용하면 HKCR에 대한 모든 작성은 HKEY\_CURRENT\_USER\(HKCU\)로 리디렉션됩니다.  사용자별 리디렉션을 해제한 경우 프로그램에서 HKCR에 대해 변경을 시도하면 [프로젝트 빌드 오류 PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md)가 발생합니다.  
  
 **라이브러리 종속성 링크**  
 종속 프로젝트가 생성한 .lib 파일에 링크하도록 선택할 수 있습니다.  일반적으로 .lib 파일에 링크합니다.  
  
 예를 들어 **..\\..\\MyLibProject\\MyObjFile.obj**와 같이 상대 경로 및 파일 이름을 제공하여.obj 파일을 지정할 수도 있습니다.  미리 컴파일된 헤더 예를 들어 pch.h 가 .obj 파일에 대한 소스 코드에 포함되어 있으면 pch.obj 파일은 같은 폴더에 **MyObjFile.obj** 로 위치하게 되고 **pch.obj** 를 추가 종속성으로 추가해야 합니다.  
  
 **라이브러리 종속성 입력 사용**  
 큰 프로젝트에서는 종속 프로젝트가 lib 파일을 생성할 때 증분 링크가 사용되지 않습니다.  .lib 파일을 생성하는 종속 프로젝트가 많이 있으면 응용 프로그램 빌드 시간이 오래 걸릴 수 있습니다.  이 속성을 `Yes`로 설정하면 프로젝트 시스템은 종속 프로젝트에서 생성한 .lib의 .obj 파일에 링크되어 증분 링크를 활성화합니다.  
  
 **일반** 링커 속성 페이지에 액세스하는 방법에 대한 자세한 내용은 [방법: 속성 페이지를 사용하여 프로젝트 속성 지정](../misc/how-to-specify-project-properties-with-property-pages.md)을 참조하십시오.  
  
## 참고 항목  
 [VC\+\+ Directories, Projects and Solutions, Options Dialog Box](http://msdn.microsoft.com/ko-kr/e027448b-c811-4c3d-8531-4325ad3f6e02)   
 [속성 페이지](../ide/property-pages-visual-cpp.md)