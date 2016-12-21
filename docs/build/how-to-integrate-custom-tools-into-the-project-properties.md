---
title: "방법: 사용자 지정 도구를 프로젝트 속성에 통합 | Microsoft Docs"
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
  - "msbuild.cpp.howto.integratecustomtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild(c++), 방법: 사용자 지정 도구 통합"
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: 사용자 지정 도구를 프로젝트 속성에 통합
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 XML 스키마 파일을 만들어 Visual Studio **속성 페이지** 창에 사용자 지정 도구 옵션을 추가할 수 있습니다.  
  
 **속성 페이지** 창의 **구성 속성** 섹션에는 *규칙*으로 알려진 설정 그룹이 표시됩니다.  각 규칙에는 도구 또는 기능 그룹에 대한 설정이 포함됩니다.  예를 들어 **링커** 규칙에는 링커 도구에 대한 설정이 포함됩니다.  규칙의 설정을 *범주*로 세분화할 수 있습니다.  
  
 이 문서에서는 Visual Studio를 시작할 때 속성이 로드되도록 사용자 지정 도구의 속성을 포함하는 파일을 설정된 사전에 만드는 방법에 대해 설명합니다.  파일을 수정하는 방법에 대한 자세한 내용은 Visual Studio Project Team 블로그에서 [Platform Extensibilty Part 2](http://go.microsoft.com/fwlink/?LinkID=191489)를 참조하십시오.  
  
### 프로젝트 속성을 추가하거나 변경하려면  
  
1.  XML 편집기에서 XML 파일을 만듭니다.  
  
2.  %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\ 폴더에 파일을 저장합니다.  **속성 페이지** 창의 각 규칙은 이 폴더의 XML 파일로 나타냅니다.  파일 이름이 폴더에서 고유한지 확인합니다.  
  
3.  %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\cl.xml의 내용을 복사하고 변경 내용을 저장하지 않고 파일을 닫은 다음 복사한 내용을 새 XML 파일에 붙여 넣습니다.  아무 XML 스키마 파일이나 사용할 수 있습니다. 이 파일은 템플릿을 시작하기 위한 용도로만 사용됩니다.  
  
4.  새 XML 파일에서 요구 사항에 따라 내용을 수정합니다.  파일 맨 위에 있는 **규칙 이름** 및 **Rule.DisplayName**을 변경해야 합니다.  
  
5.  변경 내용을 저장한 후 파일을 닫습니다.  
  
6.  Visual Studio를 시작하면 %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\의 XML 파일이 로드됩니다.  따라서 새 파일을 테스트하려면 Visual Studio를 다시 시작합니다.  
  
7.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  **속성 페이지** 창의 왼쪽 창에서 규칙 이름이 지정된 새 노드가 있는지 확인합니다.  
  
## 참고 항목  
 [MSBuild\(Visual C\+\+\)](../build/msbuild-visual-cpp.md)