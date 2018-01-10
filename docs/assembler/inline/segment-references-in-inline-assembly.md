---
title: "인라인 어셈블리의 참조 세그먼트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4aff05b82570368038965e57308b0238287586ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="segment-references-in-inline-assembly"></a>인라인 어셈블리의 세그먼트 참조
## <a name="microsoft-specific"></a>Microsoft 전용  
 이름 대신 레지스터로 세그먼트를 참조해야 합니다. 예를 들어 세그먼트 이름 `_TEXT`는 올바르지 않습니다. 세그먼트 재정의에서는 ES:[BX]와 같이 레지스터를 명시적으로 사용해야 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)