---
title: "/PDBPATH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb 파일, 경로"
  - "/PDBPATH dumpbin 옵션"
  - "PDB 파일, 경로"
  - "PDBPATH dumpbin 옵션"
  - "-PDBPATH dumpbin 옵션"
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDBPATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBPATH[:VERBOSE] filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 일치하는 .pdb 파일을 찾으려는 .dll 또는 .exe 파일의 이름입니다.  
  
 VERBOSE \(선택적 요소\)  
 .pdb 파일 찾기를 시도한 모든 디렉터리를 표시합니다.  
  
## 설명  
 \/PDBPATH는 디버거가 .pdb 파일을 검색하는 것과 동일한 경로를 따라 컴퓨터를 검색하여 *filename*에 지정된 파일과 일치하는 .pdb 파일이 있는 경우 알립니다.  
  
 Visual Studio 디버거를 사용할 경우, 디버거가 디버그 중인 파일과 다른 버전의 .pdb 파일을 사용하고 있기 때문에 문제가 발생할 수 있습니다.  
  
 \/PDBPATH는 다음과 같은 경로에서 .pdb 파일을 검색합니다.  
  
-   실행 파일이 있는 위치를 확인합니다.  
  
-   실행 파일로 작성된 PDB 위치를 확인합니다.  대개 이미지가 링크된 시점의 위치입니다.  
  
-   Visual Studio IDE에서 구성된 검색 경로를 확인합니다.  
  
-   \_NT\_SYMBOL\_PATH 및 \_NT\_ALT\_SYMBOL\_PATH 환경 변수의 경로를 확인합니다.  
  
-   Windows 디렉터리를 확인합니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)   
 [\/PDBALTPATH\(대체 PDB 경로 사용\)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)