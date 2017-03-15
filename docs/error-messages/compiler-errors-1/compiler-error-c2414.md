---
title: "컴파일러 오류 C2414 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2414"
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

피연산자 수가 잘못되었습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  opcode가 사용된 피연산자 수를 지원하지 않습니다.  어셈블리 언어 참조 설명서를 확인하여 피연산자의 올바른 수를 알아보십시오.  
  
2.  새 프로세서가 다른 피연산자 수를 사용하는 명령을 지원합니다.  나중에 프로세서를 사용할 수 있도록 [\/arch\(최소 CPU 아키텍처\)](../../build/reference/arch-minimum-cpu-architecture.md) 옵션을 조정하십시오.