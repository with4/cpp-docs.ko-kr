---
title: "어셈블리 언어 주석 | Microsoft Docs"
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
  - "__asm 키워드[C++], 명령"
  - "어셈블리 언어[C++], 주석"
  - "주석[C++], 어셈블리 언어"
  - "매크로[C++], 어셈블리 언어"
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 어셈블리 언어 주석
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 관련  
 지침에는  `__asm`블록 어셈블리 언어 주석을 사용할 수:  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 C 매크로 논리적으로 확장 하기 때문에 매크로의 주석을 어셈블리 언어를 사용 하지 마십시오.  \(참조  [\_\_asm 블록 C 매크로로 정의](../../assembler/inline/defining-asm-blocks-as-c-macros.md).\)  `__asm`블록 C 스타일 주석; 포함 될 수도 있습니다 자세한 내용은  [를 사용 하 여 C 또는 c \+ \+ \_\_asm 블록에서](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)