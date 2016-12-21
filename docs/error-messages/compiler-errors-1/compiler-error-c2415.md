---
title: "컴파일러 오류 C2415 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2415"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2415"
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2415
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

피연산자 형식이 잘못되었습니다.  
  
 opcode가 이 형식의 피연산자를 사용하지 않습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  opcode가 사용된 피연산자 수를 지원하지 않습니다.  어셈블리 언어 참조 설명서를 확인하여 피연산자의 올바른 수를 알아보십시오.  
  
2.  새 프로세서가 추가 형식의 명령을 지원합니다.  나중에 프로세서를 사용할 수 있도록 [\/arch\(최소 CPU 아키텍처\)](../../build/reference/arch-minimum-cpu-architecture.md) 옵션을 조정하십시오.