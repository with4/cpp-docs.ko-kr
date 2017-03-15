---
title: "컴파일러 경고 (수준 1) C4799 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4799"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4799"
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4799
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' 함수의 끝에 EMMS가 없습니다.  
  
 함수에 적어도 하나의 MMX 명령이 있지만 EMMS 명령이 없습니다.  멀티미디어 명령을 사용할 때에는 MMX 코드의 끝에 있는 멀티미디어 태그 단어를 정리하기 위해 EMMS 명령도 사용해야 합니다.  EMMS 명령에 대한 자세한 내용은 [Guidelines for When to Use EMMS](http://msdn.microsoft.com/ko-kr/a0c3b1e4-01a4-419c-a58f-ff1e97dea7d3)을 참조하십시오.  
  
 ivec.h를 사용할 때에는 코드에서 반환하기 전에 EMMS 명령을 제대로 실행하지 않아 C4799가 발생할 수 있습니다.  이는 이러한 헤더에 대해 false인 경고입니다.  ivec.h에 \_SILENCE\_IVEC\_C4799를 정의하여 이 경고를 해제할 수 있습니다.  그러나 이 경고를 해제함으로써 컴파일러에서 이 형식의 올바른 경고 역시 제공하지 않게 됩니다.  
  
 자세한 내용은 [Intel's MMX Instruction Set](../../assembler/inline/intel-s-mmx-instruction-set.md)을 참조하십시오.