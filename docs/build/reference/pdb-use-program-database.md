---
title: "/PDB(프로그램 데이터베이스 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdb"
  - "VC.Project.VCLinkerTool.ProgramDatabaseFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb 파일, 만들기"
  - "/PDB 링커 옵션"
  - "PDB 파일, 만들기"
  - "PDB 링커 옵션"
  - "-PDB 링커 옵션"
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDB(프로그램 데이터베이스 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDB:filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 링커에서 만든 PDB\(프로그램 데이터베이스\)의 사용자 지정 이름입니다.  기본 이름 대신 사용됩니다.  
  
## 설명  
 [\/DEBUG](../../build/reference/debug-generate-debug-info.md)가 지정되어 있으면 링커에서는 기본적으로 디버깅 정보가 포함된 PDB\(프로그램 데이터베이스\)를 만듭니다.  PDB의 기본 파일 이름은 프로그램의 기본 이름에 확장명 .pdb가 추가된 형태입니다.  
  
 \/PDB:*filename*을 사용하면 PDB 파일의 이름을 지정할 수 있습니다.  \/DEBUG를 지정하지 않은 경우에는 \/PDB 옵션이 무시됩니다.  
  
 PDB 파일의 크기는 최대 2GB가 될 수 있습니다.  
  
 자세한 내용은 [링커 입력 파일로 사용하는 .pdb 파일](../../build/reference/dot-pdb-files-as-linker-input.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **디버그** 속성 페이지를 클릭합니다.  
  
4.  **프로그램 데이터베이스 파일 생성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)