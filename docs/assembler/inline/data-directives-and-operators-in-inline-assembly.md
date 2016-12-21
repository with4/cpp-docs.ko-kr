---
title: "인라인 어셈블리에서 데이터 지시문 및 연산자 | Microsoft Docs"
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
  - "__asm 키워드[C++], 제한 사항 참조"
  - "데이터 지시문[C++]"
  - "지시문[C++], MASM"
  - "인라인 어셈블리, 데이터 지시문"
  - "인라인 어셈블리, 연산자"
  - "MASM(Microsoft Macro Assembler), 지시문"
  - "MASM(Microsoft Macro Assembler), 연산자"
  - "MASM(Microsoft Macro Assembler), 구조체"
  - "연산자[MASM]"
  - "구조체[C++], MASM"
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 어셈블리에서 데이터 지시문 및 연산자
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `__asm` 블록은 C 또는 C\+\+ 데이터 형식과 개체를 참조할 수 있지만 MASM 지시문이나 연산자를 사용하여 데이터 개체를 정의할 수 없습니다.  특히 **DB**, `DW`, **DD**, `DQ`, `DT` 및 `DF` 정의 지시문이나 `DUP` 또는 **THIS** 연산자를 사용할 수 없습니다.  MASM 구조체와 레코드도 사용할 수 없습니다.  인라인 어셈블러에서는 `STRUC`, `RECORD`, **WIDTH** 또는 **MASK** 지시문을 허용하지 않습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)