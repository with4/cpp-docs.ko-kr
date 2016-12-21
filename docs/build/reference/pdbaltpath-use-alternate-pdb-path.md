---
title: "/PDBALTPATH(대체 PDB 경로 사용) | Microsoft Docs"
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
  - "/pdbaltpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb 파일, 경로"
  - "/PDBALTPATH dumpbin 옵션"
  - "PDB 파일, 경로"
  - "PDBALTPATH dumpbin 옵션"
  - "-PDBALTPATH dumpbin 옵션"
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBALTPATH(대체 PDB 경로 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBALTPATH:pdb_file_name  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *pdb\_file\_name*  
 .pdb 파일의 경로 및 파일 이름입니다.  
  
## 설명  
 이 옵션은 컴파일된 이진 파일에서 프로그램 데이터베이스\(.pdb\) 파일의 대체 위치를 제공하는 데 사용합니다.  일반적으로 링커는 자신이 생성한 이진 파일에 .pdb 파일의 위치를 기록합니다.  이 옵션을 사용하여 .pdb 파일의 다른 경로 및 파일 이름을 제공할 수 있습니다.  \/PDBALTPATH와 함께 제공되는 정보는 실제 .pdb 파일의 위치 또는 이름을 변경하지 않고 링커가 이진 파일에 쓴 정보를 변경합니다.  따라서 빌드 컴퓨터의 파일 구조와 독립적인 경로를 제공할 수 있습니다.  이 옵션은 일반적으로 네트워크 경로 또는 경로 정보가 없는 파일을 제공하는 두 가지 용도로 사용됩니다.  
  
 *pdb\_file\_name*의 값은 임의 문자열, 환경 변수 또는 **%\_PDB%**일 수 있습니다.  링커는 **%SystemRoot%**와 같은 환경 변수를 해당 값으로 확장합니다.  링커는 환경 변수 **%\_PDB%** 및 **%\_EXT%**를 정의합니다.  **%\_PDB%**는 경로 정보가 없는 실제 .pdb 파일의 파일 이름으로 확장되고 **%\_EXT%**는 생성된 실행 파일의 확장명이 됩니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)   
 [\/PDBPATH](../../build/reference/pdbpath.md)