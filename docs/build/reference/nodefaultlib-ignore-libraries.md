---
title: "/NODEFAULTLIB(라이브러리 무시) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames"
  - "/nodefaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NODEFAULTLIB 링커 옵션"
  - "기본 라이브러리, 제거"
  - "라이브러리 링커 옵션 무시"
  - "라이브러리, 무시"
  - "NODEFAULTLIB 링커 옵션"
  - "-NODEFAULTLIB 링커 옵션"
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /NODEFAULTLIB(라이브러리 무시)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NODEFAULTLIB[:library]   
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *library*  
 링커에서 외부 참조를 확인할 때 무시하도록 할 라이브러리입니다.  
  
## 설명  
 \/NODEFAULTLIB 옵션을 사용하면 외부 참조를 확인할 때 검색하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거하도록 링커에 지시할 수 있습니다.  
  
 기본 라이브러리에 대한 참조가 없는 .obj 파일을 만들려면 [\/Zl\(기본 라이브러리 이름 생략\)](../../build/reference/zl-omit-default-library-name.md)을 사용합니다.  
  
 기본적으로 \/NODEFAULTLIB는 외부 참조를 확인할 때 검색하는 라이브러리 목록에서 모든 기본 라이브러리를 제거합니다.  선택적 매개 변수인 *library*를 사용하면 외부 참조를 확인할 때 검색하는 라이브러리 목록에서 지정된 라이브러리를 제거할 수 있습니다.  제외시킬 각 라이브러리에 대해 \/NODEFAULTLIB 옵션을 한 번씩 지정합니다.  
  
 링커에서는 사용자가 명시적으로 지정한 라이브러리에서 먼저 검색한 다음 \/DEFAULTLIB 옵션으로 지정된 기본 라이브러리와 .obj 파일에 지정된 기본 라이브러리에서 차례로 검색하는 방법으로 외부 정의에 대한 참조를 확인합니다.  
  
 또한 \/NODEFAULTLIB:*library*를 사용하는 경우 동일한 *library* 이름이 지정된 [\/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*library*는 무시됩니다.  
  
 예를 들어, \/NODEFAULTLIB를 사용하여 C 런타임 라이브러리 없이 프로그램을 빌드하는 경우 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)도 사용하여 프로그램에 진입점\(함수\)을 지정해야 합니다.  자세한 내용은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **입력** 속성 페이지를 클릭합니다.  
  
4.  **모든 기본 라이브러리 무시** 속성을 선택하거나 **특정 라이브러리 무시** 속성에 무시하려는 라이브러리 목록을 지정합니다.  **명령줄** 속성 페이지가 이들 속성에 대한 변경 내용의 효과를 보여 줍니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)