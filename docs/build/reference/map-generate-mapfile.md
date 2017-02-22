---
title: "/MAP(맵파일 생성) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/map"
  - "VC.Project.VCLinkerTool.MapFileName"
  - "VC.Project.VCLinkerTool.GenerateMapFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MAP 링커 옵션"
  - "맵 파일 생성 링커 옵션"
  - "MAP 링커 옵션"
  - "-MAP 링커 옵션"
  - "맵 파일 링커 옵션"
  - "맵 파일, 링커 만들기"
  - "맵 파일, 링크될 프로그램에 대한 정보"
  - "맵 파일, 파일 이름 지정"
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MAP(맵파일 생성)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MAP[:filename]  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 맵 파일의 사용자 지정 이름입니다.  기본 이름 대신 사용됩니다.  
  
## 설명  
 \/MAP 옵션을 사용하면 맵 파일을 만들도록 링커에 지시할 수 있습니다.  
  
 기본적으로 링커에서는 프로그램의 기본 이름과 확장명 .map을 사용하여 맵 파일의 이름을 지정합니다.  선택적 인수인 *filename*을 사용하면 맵 파일의 기본 이름을 무시할 수 있습니다.  
  
 맵 파일은 링크되는 프로그램에 대한 다음 정보가 포함된 텍스트 파일입니다.  
  
-   파일의 기본 이름인 모듈 이름  
  
-   파일 시스템이 아니라 프로그램 파일 헤더의 타임스탬프  
  
-   프로그램의 그룹 목록. 각 그룹의 시작 주소\(*section*:*offset*\), 길이, 그룹 이름 및 클래스가 함께 표시됩니다.  
  
-   공용 기호 목록. 각 주소\(*section*:*offset*\), 기호 이름, 플랫 주소, 기호가 정의된 .obj 파일이 함께 표시됩니다.  
  
-   진입점\(*section*:*offset*\)  
  
 [\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) 옵션을 사용하면 맵 파일에 포함시킬 추가 정보를 지정할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **디버그** 속성 페이지를 클릭합니다.  
  
4.  **맵 파일 생성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)