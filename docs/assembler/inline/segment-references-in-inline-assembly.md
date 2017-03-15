---
title: "인라인 어셈블리에서 세그먼트 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인라인 어셈블리, 레지스터"
  - "인라인 어셈블리, 세그먼트 참조"
  - "참조, 인라인 어셈블리"
  - "레지스터"
  - "레지스터, 인라인 어셈블리"
  - "인라인 어셈블리의 세그먼트 참조"
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 인라인 어셈블리에서 세그먼트 참조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 이름 대신 레지스터로 세그먼트를 참조해야 합니다. 예를 들어 세그먼트 이름 `_TEXT`는 올바르지 않습니다.  세그먼트 재정의에서는 ES:\[BX\]와 같이 레지스터를 명시적으로 사용해야 합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)