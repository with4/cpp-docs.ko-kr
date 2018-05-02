---
title: 인라인 어셈블리의 MASM 매크로 지시문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfd8e3ca5fb6bf65a288c17b1754d567b2b081a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="masm-macro-directives-in-inline-assembly"></a>인라인 어셈블리의 MASM 매크로 지시문
## <a name="microsoft-specific"></a>Microsoft 전용  
 인라인 어셈블러는 매크로 어셈블러가 아닙니다. MASM 매크로 지시문을 사용할 수 없습니다 (**매크로**, `REPT`, **IRC**, `IRP`, 및 `ENDM`) 또는 매크로 연산자 (**<>**, **!** , **&**, `%`, 및 `.TYPE`). 그러나 `__asm` 블록에 C 전처리기 지시문을 사용할 수 있습니다. 참조 [C를 사용 하 여 또는 __asm 블록에서 c + +](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) 자세한 정보에 대 한 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)