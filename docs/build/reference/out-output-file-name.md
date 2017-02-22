---
title: "/OUT(출력 파일 이름) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OutputFile"
  - "/out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OUT C++ 링커 옵션"
  - "링커[C++], 출력 파일"
  - "OUT 링커 옵션"
  - "-OUT 링커 옵션"
  - "출력 파일, 이름 링커 옵션"
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /OUT(출력 파일 이름)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/OUT:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 출력 파일의 사용자 지정 이름입니다.  기본 이름 대신 사용됩니다.  
  
## 설명  
 \/OUT 옵션을 사용하면 링커에서 만드는 프로그램의 기본 이름과 위치는 무시됩니다.  
  
 기본적으로 링커에서는 첫 번째로 지정된 .obj 파일의 기본 이름과 적절한 확장명\(.exe 또는 .dll\)을 사용하여 파일 이름을 지정합니다.  
  
 이 옵션은 .mapfile이나 가져오기 라이브러리의 기본 이름을 대체합니다.  자세한 내용은 [맵 파일 생성](../../build/reference/map-generate-mapfile.md)\(\/MAP\) 및 [\/IMPLIB](../../build/reference/implib-name-import-library.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **출력 파일** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)