---
title: "XML 문서 생성기 도구 속성 페이지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs: C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66d6cd4359cfe4700f7decf0ec54686a4b70a183
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="xml-document-generator-tool-property-pages"></a>XML 문서 생성기 도구 속성 페이지
XML 문서 생성기 도구 속성 페이지 xdcmake.exe의 기능을 제공 합니다. 소스 코드에는 문서 주석을 포함 하는 경우 xdcmake.exe.xml 파일로.xdc 파일을 병합 하 고 [/doc (문서 주석 처리) (C/c + +)](../build/reference/doc-process-documentation-comments-c-cpp.md) 를 지정 합니다. 참조 [문서 주석에 대 한 권장 태그](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) 내용은 소스 코드에 문서 주석을 추가 합니다.  
  
> [!NOTE]
>  개발 환경 (속성 페이지)의 xdcmake.exe 옵션 xdcmake.exe 명령줄에서 사용 되는 경우 옵션 중에서 다릅니다. 명령줄에서 xdcmake.exe를 사용 하는 방법은 참조 하십시오. [XDCMake 참조](../ide/xdcmake-reference.md)합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **시작 배너 표시 안 함**  
 저작권 메시지를 표시 합니다.  
  
 **추가 문서 파일**  
 프로젝트 시스템에.xdc 파일을 찾도록 할 추가 디렉터리입니다. xdcmake은 항상 프로젝트에서 생성 된.xdc 파일 검색 합니다. 여러 디렉터리를 지정할 수 있습니다.  
  
 **출력 문서 파일**  
 .Xml 출력 파일의 이름과 디렉터리 위치입니다. 참조 [빌드 명령 및 속성에 대 한 일반적인 매크로](../ide/common-macros-for-build-commands-and-properties.md) 매크로 사용 하 여 디렉터리 위치를 지정 하는 방법은 합니다.  
  
 **라이브러리 종속성 문서화**  
 프로젝트 솔루션에서.lib 프로젝트에 종속 하는 경우에 현재 프로젝트에 대 한.xml 파일에.lib 프로젝트에서.xdc 파일을 처리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)   
 [속성 페이지](../ide/property-pages-visual-cpp.md)