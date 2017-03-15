---
title: "/PDBSTRIPPED(전용 기호 제거) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbstripped"
  - "VC.Project.VCLinkerTool.StripPrivateSymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb 파일, 전용 기호 제거"
  - "/PDBSTRIPPED 링커 옵션"
  - "PDB 파일, 전용 기호 제거"
  - "PDBSTRIPPED 링커 옵션"
  - "-PDBSTRIPPED 링커 옵션"
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDBSTRIPPED(전용 기호 제거)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *pdb\_file\_name*  
 링커에서 만든 스트리핑된 PDB\(프로그램 데이터베이스\)의 사용자 지정 이름입니다.  
  
## 설명  
 \/PDBSTRIPPED 옵션을 사용하면 PDB 파일을 생성하는 컴파일러 또는 링커 옵션\([\/DEBUG](../../build/reference/debug-generate-debug-info.md), [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), \/Zd 또는 \/Zi\)으로 프로그램 이미지를 빌드할 때 두 번째 PDB\(프로그램 데이터베이스\)가 만들어집니다.  이 두 번째 PDB 파일에서는 고객에게 제공하지 않을 기호가 생략됩니다.  두 번째 PDB 파일에는 다음 내용만 포함됩니다.  
  
-   공용 기호  
  
-   개체 파일의 목록과 개체 파일에서 제공하는 실행 파일의 일부  
  
-   스택을 통과시키는데 사용된 FPO\(프레임 포인터 최적화\) 디버그 레코드  
  
 스트립된 PDB 파일에는 다음 내용이 포함되지 않습니다.  
  
-   형식 정보  
  
-   줄 번호 정보  
  
-   개체 파일별 CodeView 기호\(함수, 지역 및 정적 데이터에 대한 기호 등\)  
  
 \/PDBSTRIPPED를 사용하는 경우에도 완전한 PDB 파일이 생성됩니다.  
  
 PDB 파일을 만들지 않으면 \/PDBSTRIPPED는 무시됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **디버그** 속성 페이지를 클릭합니다.  
  
4.  **전용 기호 제거** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)