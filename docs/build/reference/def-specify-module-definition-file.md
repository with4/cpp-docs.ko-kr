---
title: "/DEF(모듈 정의 파일 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ModuleDefinitionFile"
  - "/def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEF 링커 옵션"
  - "DEF 링커 옵션"
  - "-DEF 링커 옵션"
  - "모듈 정의 파일"
  - "모듈 정의 파일, 지정"
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /DEF(모듈 정의 파일 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEF:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 링커에 전달될 모듈 정의 파일\(.def\)의 이름입니다.  
  
## 설명  
 \/DEF 옵션으로 모듈 정의 파일\(.def\)을 링커에 전달합니다.  .def 파일은 LINK에 대해 하나만 지정할 수 있습니다.  .def 파일에 대한 자세한 내용은 [모듈 정의\(.def\) 파일](../../build/reference/module-definition-dot-def-files.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **입력** 속성 페이지를 클릭합니다.  
  
4.  **모듈 정의 파일** 속성을 수정합니다.  
  
 개발 환경에서 .def 파일을 지정하려면 .def 파일을 다른 파일과 함께 프로젝트에 추가한 다음 해당 파일을 \/DEF 옵션에 지정해야 합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)