---
title: "/c(링크 없이 컴파일) | Microsoft Docs"
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
  - "/c"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c 컴파일러 옵션[C++]"
  - "c 컴파일러 옵션[C++]"
  - "-c 컴파일러 옵션[C++]"
  - "cl.exe 컴파일러, 링크하지 않고 컴파일"
  - "링크 표시하지 않음"
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /c(링크 없이 컴파일)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK가 자동으로 호출되지 않도록 합니다.  
  
## 구문  
  
```  
/c  
```  
  
## 설명  
 **\/c**로 컴파일하면 .obj 파일만 만들어집니다.  빌드에서 링크 단계를 수행하려면 적절한 파일과 옵션을 사용하여 명시적으로 LINK를 호출해야 합니다.  
  
 개발 환경에서 만든 내부 프로젝트에서는 기본적으로 **\/c** 옵션을 사용합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
-   개발 환경에서는 이 옵션을 사용할 수 없습니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄은 FIRST.obj 및 SECOND.obj 개체 파일을 만듭니다.  THIRD.obj는 무시됩니다.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 실행 파일을 만들려면 다음과 같이 LINK를 호출해야 합니다.  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)