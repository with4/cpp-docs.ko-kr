---
title: "방법: 프로젝트 속성에 사용자 지정 도구 통합 | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a762fc573953bcfb09180b9b830b761448d87a0d
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>방법: 사용자 지정 도구를 프로젝트 속성에 통합
Visual Studio를 사용자 지정 도구 옵션을 추가할 수 있습니다 **속성 페이지** 기본 XML 스키마 파일을 만들어 창.  
  
 **구성 속성** 의 섹션은 **속성 페이지** 이라고 하는 설정 그룹 창에 표시 됩니다 *규칙*합니다. 모든 규칙에는 도구 또는 기능 그룹에 대 한 설정을 포함합니다. 예를 들어는 **링커** 규칙 링커 도구에 대 한 설정을 포함 합니다. 규칙의 설정을 분할할 수 있습니다 *범주*합니다.  
  
 이 문서는 속성은 Visual Studio가 시작 될 때 로드 되도록 사용자 지정 도구에 대 한 속성을 포함 하는 디렉터리 설정에에서는 파일을 만드는 방법에 설명 합니다. 파일을 수정 하는 방법에 대 한 정보를 참조 하십시오. [플랫폼 확장성 2 부](http://go.microsoft.com/fwlink/p/?linkid=191489) Visual Studio 프로젝트 팀 블로그.  
  
### <a name="to-add-or-change-project-properties"></a>추가 하거나 프로젝트 속성을 변경 하려면  
  
1.  XML 편집기에서 XML 파일을 만듭니다.  
  
2.  Visual Studio 2017에 파일을 저장 `VCTargets\1033` 폴더입니다. 설치 된 Visual Studio 2017의 각 버전 및 각 언어에 대 한 다른 경로 갖습니다. 예를 들어 영어로 Visual Studio Enterprise edition의 폴더 경로 `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`합니다. 언어와 Visual Studio 버전에 대 한 경로 조정 합니다. 모든 규칙의 **속성 페이지** 창이이 폴더에 XML 파일로 표시 됩니다. 파일 폴더에 이름이 고유 하 게 있는지 확인 합니다.  
  
3.  콘텐츠 복사 `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`, 변경 내용을 저장 하지 않고 닫은 다음 콘텐츠를 새 XML 파일에 붙여 넣습니다. 모든 XML 스키마 파일을 사용할 수 있습니다-이것은 하나는 템플릿으로 시작 하므로 사용할 수 있는 합니다.  
  
4.  새 XML 파일에서 요구 사항에 따라 콘텐츠를 수정 합니다. 변경할 수 있는지 확인은 **규칙 이름** 및 **Rule.DisplayName** 파일 맨 위에 있는 합니다.  
  
5.  변경 내용을 저장 하 고 파일을 닫습니다.  
  
6.  XML 파일에 `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` Visual Studio가 시작 될 때 로드 됩니다. 따라서 새 파일을 테스트 하려면 Visual Studio를 다시 시작 하십시오.  
  
7.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 에 **속성 페이지** 창의 왼쪽된 창에서 규칙의 이름으로 새 노드에 있는지 확인 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild(Visual C++)](../build/msbuild-visual-cpp.md)
