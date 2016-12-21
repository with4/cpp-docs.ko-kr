---
title: "EVEN 및 ALIGN 지시문 | Microsoft Docs"
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
  - "align"
  - "EVEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIGN 지시문"
  - "지시문, MASM"
  - "EVEN 지시문"
  - "MASM(Microsoft Macro Assembler), 지시문"
  - "NOP(작업 없음 명령)"
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EVEN 및 ALIGN 지시문
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 인라인 어셈블리가 대부분의 MASM 지시문을 지원하지 않지만 `EVEN` 및 **ALIGN**을 지원합니다.  이러한 지시문은 레이블을 특정 경계에 배열하는 데 필요하도록 **NOP**\(비연산\) 명령을 어셈블리 코드에 배치합니다.  이를 통해 일부 프로세서에서 명령 페치 작업을 보다 효율적으로 수행할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)