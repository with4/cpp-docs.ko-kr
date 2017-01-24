---
title: "/DEBUG(디버깅 정보 생성) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.GenerateDebugInformation"
  - "/debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb 파일, 디버그 정보 생성"
  - "/DEBUG 링커 옵션"
  - "DEBUG 링커 옵션"
  - "-DEBUG 링커 옵션"
  - "디버깅[C++], 디버그 정보 파일"
  - "디버깅[C++], 링커 옵션"
  - "디버그 정보 생성 링커 옵션"
  - "PDB 파일"
  - "pdb 파일, 디버그 정보 생성"
  - "프로그램 데이터베이스[C++]"
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEBUG(디버깅 정보 생성)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEBUG  
```  
  
## 설명  
 \/DEBUG 옵션을 사용하면 .exe 파일이나 DLL에 대한 디버깅 정보가 만들어집니다.  
  
 링커에서는 PDB\(프로그램 데이터베이스\)에 디버깅 정보를 보관하고,  해당 프로그램의 후속 빌드 과정에서 이 PDB를 업데이트합니다.  
  
 디버깅을 위해 만든 .exe 파일이나 DLL에는 해당 PDB의 이름과 경로가 포함됩니다.  프로그램을 디버깅하면 디버거에서는 이 포함된 이름을 읽고 PDB를 사용합니다.  링커에서는 프로그램의 기본 이름과 확장명 .pdb를 사용하여 프로그램 데이터베이스의 이름을 지정하고 프로그램 데이터베이스의 생성 경로를 포함시킵니다.  이 기본값을 사용하지 않으려면 [\/PDB](../../build/reference/pdb-use-program-database.md)를 설정하고 다른 파일 이름을 지정합니다.  
  
 컴파일러의 [줄 번호만](../../build/reference/z7-zi-zi-debug-information-format.md)\(\/Zd\) 또는 [C7 호환](../../build/reference/z7-zi-zi-debug-information-format.md)\(\/Z7\) 옵션을 사용하면 디버깅 정보가 .obj 파일에 남게 됩니다.  [프로그램 데이터베이스](../../build/reference/z7-zi-zi-debug-information-format.md)\(\/Zi\) 컴파일러 옵션을 사용하여 디버깅 정보를 .obj 파일에 대한 PDB에 저장할 수도 있습니다.  링커는 해당 개체의 PDB를 먼저 .obj 파일에 기록된 절대 경로에서 찾은 다음 .obj 파일이 들어 있는 디렉터리에서 찾습니다.  개체의 PDB 파일 이름이나 위치를 링커에 지정할 수는 없습니다.  
  
 \/DEBUG를 지정하면 [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)도 지정됩니다.  
  
 \/DEBUG는 [\/OPT](../../build/reference/opt-optimizations.md) 옵션의 기본값을 REF에서 NOREF로 변경하고 ICF에서 NOICF로 변경합니다. 따라서 \/OPT:REF나 \/OPT:ICF는 명시적으로 지정해야 합니다.  
  
 .PDB 파일과 .DBG 파일에 대한 자세한 내용은 기술 자료 문서 INFO: PDB and DBG Files \- What They Are and How They Work\(Q121366\)를 참조하십시오.  기술 자료 문서는 MSDN 라이브러리 또는 [http:\/\/support.microsoft.com](http://support.microsoft.com/)에 있습니다.  
  
 디버그 정보가 포함된 .exe나 .dll은 만들 수 없습니다.  디버그 정보는 항상 .pdb 파일에 저장됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **Debugging**  속성 페이지를 클릭합니다.  
  
4.  **디버그 정보 생성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)