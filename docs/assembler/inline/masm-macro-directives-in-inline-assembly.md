---
title: "인라인 어셈블리에서 MASM 매크로 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "지시문, 매크로"
  - "인라인 어셈블리, 매크로 지시문"
  - "매크로, 지시문"
  - "MASM(Microsoft Macro Assembler), 인라인 어셈블리 매크로 지시문"
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 어셈블리에서 MASM 매크로 지시문
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 인라인 어셈블러는 매크로 어셈블러가 아닙니다.  MASM 매크로 지시문\(**MACRO**, `REPT`, **IRC**, `IRP` 및 `ENDM`\) 또는 매크로 연산자\(**\<\>**, **\!**, **&**, `%` 및 `.TYPE`\)를 사용할 수 없습니다.  그러나 `__asm` 블록에 C 전처리기 지시문을 사용할 수 있습니다.  자세한 내용은 [\_\_asm 블록에서 C 또는 C\+\+ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)을 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)