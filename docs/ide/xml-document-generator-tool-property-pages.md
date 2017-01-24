---
title: "XML 문서 생성기 도구 속성 페이지 | Microsoft Docs"
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
  - "VC.Project.VCXDCMakeTool.ValidateIntelliSense"
  - "VC.Project.VCXDCMakeTool.SuppressStartupBanner"
  - "VC.Project.VCXDCMakeTool.DocumentLibraryDependencies"
  - "VC.Project.VCXDCMakeTool.OutputDocumentFile"
  - "VC.Project.VCXDCMakeTool.AdditionalDocumentFiles"
dev_langs: 
  - "C++"
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XML 문서 생성기 도구 속성 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

XML 문서 생성기 도구 속성 페이지는 xdcmake.exe의 기능을 노출합니다.  소스 코드에 문서 주석이 포함되고 [\/doc\(문서 주석 처리\)](../build/reference/doc-process-documentation-comments-c-cpp.md)이 지정되면 xdcmake.exe는 .xdc 파일을 .xml 파일로 병합합니다.  문서 주석을 소스 코드에 추가하는 방법에 대한 내용은 [문서 주석에 대한 권장 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)를 참조하십시오.  
  
> [!NOTE]
>  개발 환경의 xdcmake.exe 옵션\(속성 페이지\)은 명령줄에서 xdcmake.exe가 사용될 때의 옵션과 다릅니다.  명령줄에서 xdcmake.exe를 사용하는 방법에 대한 내용은 [XDCMake 참조](../ide/xdcmake-reference.md)를 참조하십시오.  
  
## UI 요소 목록  
 **시작 배너 표시 안 함**  
 저작권 메시지를 표시하지 않습니다.  
  
 **추가 문서 파일**  
 프로젝트 시스템이 .xdc 파일을 찾을 추가 디렉터리입니다.  항상 xdcmake는 프로젝트에서 생성된 .xdc 파일을 찾습니다.  디렉터리를 여러 개 지정할 수 있습니다.  
  
 **출력 문서 파일**  
 .xml 출력 파일의 이름과 디렉터리 위치입니다.  매크로를 사용하여 디렉터리 위치를 지정하는 방법에 대한 내용은 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)를 참조하십시오.  
  
 **라이브러리 종속성 문서화**  
 프로젝트가 솔루션의 .lib 프로젝트에 종속적인 경우 .lib 프로젝트의 .xdc 파일을 현재 프로젝트에 대한 .xml 파일로 만들 수 있습니다.  
  
## 참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [속성 페이지](../ide/property-pages-visual-cpp.md)