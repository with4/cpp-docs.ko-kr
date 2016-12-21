---
title: "NMAKE 심각한 오류 U1099 | Microsoft Docs"
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
  - "U1099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1099"
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 심각한 오류 U1099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택 오버플로입니다.  
  
 처리할 메이크파일은 NMAKE의 현재 스택 할당에 대해 너무 복잡합니다.  NMAKE는 0x3000\(12K\)을 할당합니다.  
  
 NMAKE의 스택 할당을 증가시키려면 큰 스택 옵션으로 [editbin \/STACK](../../build/reference/stack.md) 유틸리티를 실행합니다.  
  
 **editbin \/STACK:reserve NMAKE.EXE**  
  
 여기에 *reserve*는 NMAKE에서 현재 스택 할당보다 큰 숫자입니다.