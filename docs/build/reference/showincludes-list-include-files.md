---
title: "/showIncludes(포함 파일 나열) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.ShowIncludes"
  - "VC.Project.VCCLCompilerTool.ShowIncludes"
  - "/showincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/showIncludes 컴파일러 옵션[C++]"
  - "포함 파일"
  - "포함 파일, 컴파일에 표시"
  - "showIncludes 컴파일러 옵션[C++]"
  - "-showIncludes 컴파일러 옵션[C++]"
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /showIncludes(포함 파일 나열)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 포함 파일 목록을 출력합니다.  중첩 포함 파일\(포함한 파일에 포함된 파일\)도 표시됩니다.  
  
## 구문  
  
```  
/showIncludes  
```  
  
## 설명  
 컴파일하는 동안 포함 파일이 나타나면 다음과 같이 메시지가 출력됩니다.  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 중첩 포함 파일은 중첩된 각 수준마다 한 칸씩 들여써서 나타냅니다. 예를 들면 다음과 같습니다.  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 이 경우 `2.h`는 `1.h` 내에 포함되므로 들여씁니다.  
  
 **\/showIncludes** 옵션의 출력은 `stdout`이 아닌 `stderr`로 보내집니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **포함 표시** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)