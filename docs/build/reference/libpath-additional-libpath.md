---
title: "/LIBPATH(추가 Libpath) | Microsoft Docs"
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
  - "/libpath"
  - "VC.Project.VCLinkerTool.AdditionalLibraryDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LIBPATH 링커 옵션"
  - "추가 Libpath 링커 옵션"
  - "환경 라이브러리 경로 재정의"
  - "LIBPATH 링커 옵션"
  - "-LIBPATH 링커 옵션"
  - "라이브러리 경로 링커 옵션"
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LIBPATH(추가 Libpath)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LIBPATH:dir  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `dir`  
 링커에서 LIB 환경 옵션으로 지정된 경로를 검색하기 전에 먼저 검색할 경로를 지정합니다.  
  
## 설명  
 \/LIBPATH 옵션을 사용하면 환경 라이브러리 경로를 재정의할 수 있습니다.  링커에서는 이 옵션으로 지정된 경로에서 먼저 검색한 다음 LIB 환경 변수로 지정된 경로에서 검색합니다.  \/LIBPATH 옵션을 입력할 때마다 디렉터리는 하나만 지정할 수 있습니다.  디렉터리를 둘 이상 지정하려면 \/LIBPATH 옵션을 여러 개 지정해야 합니다.  링커에서는 지정된 순서대로 디렉터리를 검색합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **추가 라이브러리 디렉터리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)