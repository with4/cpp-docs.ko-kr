---
title: "EVEN 및 ALIGN 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- align
- EVEN
dev_langs: C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 278794e0105ee054fdd4948967a78982a9d46d8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="even-and-align-directives"></a>EVEN 및 ALIGN 지시문
## <a name="microsoft-specific"></a>Microsoft 전용  
 인라인 어셈블러에서 대부분의 MASM 지시문을 지원 하지 않을 수 있지만 지원지 않습니다 `EVEN` 및 **맞춤**합니다. 이러한 지시문 배치 **NOP** (비 연산) 레이블을 특정 경계에 맞게 필요에 따라 어셈블리 코드에 지시 합니다. 이를 통해 일부 프로세서에서 명령 페치 작업을 보다 효율적으로 수행할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)