---
title: "DUMPBIN 명령줄 | Microsoft Docs"
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
  - "dumpbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DUMPBIN 프로그램, 명령줄"
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DUMPBIN 명령줄
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DUMPBIN을 실행하려면 다음 구문을 사용합니다.  
  
```  
DUMPBIN [options] files...  
```  
  
 정보 제어에 필요한 옵션과 함께 하나 이상의 이진 파일을 지정합니다.  DUMPBIN은 표준 출력에 정보를 표시합니다.  이것을 파일로 리디렉션하거나 \/OUT 옵션을 사용하여 출력 파일 이름을 지정할 수 있습니다.  
  
 옵션 없이 파일만 지정하여 DUMPBIN을 실행할 경우 DUMPBIN은 \/SUMMARY 출력을 표시합니다.  
  
 다른 명령줄 입력 없이 `dumpbin` 명령을 입력할 경우 옵션을 요약한 DUMPBIN의 사용법 문이 표시됩니다.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)   
 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)