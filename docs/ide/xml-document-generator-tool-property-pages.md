---
title: XML 문서 생성기 도구 속성 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs:
- C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 772e9dc6a296873ef27171676ebca0c185c1771c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33339078"
---
# <a name="xml-document-generator-tool-property-pages"></a>XML 문서 생성기 도구 속성 페이지
XML 문서 생성기 도구 속성 페이지는 xdcmake.exe의 기능을 제공합니다. xdcmake.exe는 소스 코드에 문서 주석이 있고 [/doc(문서 주석 처리) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)가 지정된 경우 .xdc 파일을 .xml 파일에 병합합니다. 문서 주석을 소스 코드에 추가하는 방법에 대한 내용은 [문서 주석에 권장되는 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)를 참조하세요.  
  
> [!NOTE]
>  개발 환경(속성 페이지)의 xdcmake.exe 옵션은 xdcmake.exe가 명령줄에서 사용될 때의 옵션과 다릅니다. 명령줄에서 xdcmake.exe를 사용하는 방법에 대한 자세한 내용은 [XDCMake 참조](../ide/xdcmake-reference.md)를 참조하세요.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **시작 배너 표시 안 함**  
 저작권 메시지를 표시하지 않습니다.  
  
 **추가 문서 파일**  
 프로젝트 시스템에서 .xdc 파일을 검색할 추가 디렉터리. xdcmake는 항상 프로젝트에서 생성한 .xdc 파일을 찾습니다. 여러 디렉터리를 지정할 수 있습니다.  
  
 **출력 문서 파일**  
 .xml 출력 파일의 이름과 디렉터리 위치. 매크로를 사용하여 디렉터리 위치를 지정하는 방법에 대한 자세한 내용은 [빌드 명령 및 속성에 대한 일반 매크로](../ide/common-macros-for-build-commands-and-properties.md)를 참조하세요.  
  
 **문서 라이브러리 종속성**  
 프로젝트가 솔루션의 .lib 프로젝트에 종속되어 있는 경우 .lib 프로젝트의 .xdc 파일을 현재 프로젝트의 .xml 파일로 처리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [속성 페이지](../ide/property-pages-visual-cpp.md)