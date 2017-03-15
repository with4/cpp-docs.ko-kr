---
title: "HLSL 속성 페이지: 출력 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.FXCompilerTool.AssemblerOutput"
  - "VC.Project.FXCompilerTool.ObjectFileOutput"
  - "VC.Project.FXCompilerTool.HeaderFileOutput"
  - "VC.Project.FXCompilerTool.VariableName"
  - "VC.Project.FXCompilerTool.AssemblerOutputFile"
dev_langs: 
  - "C++"
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
caps.latest.revision: 5
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 5
---
# HLSL 속성 페이지: 출력 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HLSL 컴파일러 \(fxc.exe\)의 다음과 같은 속성을 구성 하려면 해당  **출력 파일** 속성입니다.  에 액세스 하는 방법에 대 한 정보는  **출력 파일** HLSL 폴더에서 속성 페이지를 참조 하십시오. [방법: 속성 페이지로 프로젝트 속성 지정](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## UI 요소 목록  
 **헤더 변수 이름**  
 인코딩된 HLSL 개체 코드를 사용 하 여 배열의 이름을 지정 합니다.  배열 출력 되는 헤더 파일에 HLSL 컴파일러에 의해 포함 되어 있습니다.  지정 된 헤더 파일의 이름에  **헤더 파일 이름** 을 속성.  
  
 이 속성에 해당 하는 **\/Vn\[name\]** 명령줄 인수입니다.  
  
 **헤더 파일 이름**  
 HLSL 컴파일러에서 출력 되는 헤더 파일의 이름을 지정 합니다.  헤더 배열에 인코딩 되는 HLSL 개체 코드를 포함 합니다.  지정한 이름의 배열에  **헤더 변수 이름** 속성입니다.  
  
 이 속성에 해당 하는 **\/Fh\[name\]** 명령줄 인수입니다.  
  
 **개체 파일 이름**  
 출력 하는 HLSL 컴파일러에서 개체 파일의 이름을 지정 합니다.  기본적으로 값입니다  **$\(OutDir\)는 % \(Filename\).cso**.  
  
 이 속성에 해당 하는 **\/Fo\[name\]** 명령줄 인수입니다.  
  
 **어셈블러 출력**  
 **어셈블리 전용 목록 \(\/ Fc\)** 방금 어셈블리 언어 명령문을 출력 합니다.  **어셈블리 코드와 16 진수 \(\/ Fx\)** 16 진수에서 해당 op 코드와 어셈블리 언어 명령문을 출력 합니다.  기본적으로 표시 되지 않습니다 출력 됩니다.  
  
 **어셈블러 출력 파일**  
 HLSL 컴파일러에서 출력 어셈블리 목록 파일의 이름을 지정 합니다.  
  
 이 속성에 해당 하는 **\/Fc\[name\]** 및 **\/Fx \[name\]** 명령줄 인수입니다.  
  
## 참고 항목  
 [HLSL 속성 페이지](../ide/hlsl-property-pages.md)   
 [HLSL 속성 페이지: 일반](../ide/hlsl-property-pages-general.md)   
 [HLSL 속성 페이지: 고급](../ide/hlsl-property-pages-advanced.md)