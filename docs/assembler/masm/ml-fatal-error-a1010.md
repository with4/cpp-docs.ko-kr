---
title: ML 심각한 오류 A1010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b622595b6994c4c4eaa74ed8f824f28dffe89b1a
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057684"
---
# <a name="ml-fatal-error-a1010"></a>ML 심각한 오류 A1010
**일치 하지 않는 블록 중첩:**  
  
 블록 시작 하는 일치 하는 끝 없는 또는 블록의 끝 일치 하는 시작 되지 않았습니다. 다음 중 하나는 포함 될 수도 있습니다.  
  
-   와 같은 개략적인 지시문 [합니다. IF](../../assembler/masm/dot-if.md), [합니다. 반복](../../assembler/masm/dot-repeat.md), 또는 [합니다. 반면](../../assembler/masm/dot-while.md)합니다.  
  
-   와 같은 조건부 어셈블리 지시문 [IF](../../assembler/masm/if-masm.md), [반복](../../assembler/masm/repeat.md), 또는 **동안**합니다.  
  
-   구조체 또는 공용 구조체 정의입니다.  
  
-   프로시저 정의 합니다.  
  
-   세그먼트 정의 합니다.  
  
-   A [POPCONTEXT](../../assembler/masm/popcontext.md) 지시문입니다.  
  
-   조건부 어셈블리 지시문과 같은 [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), 또는 **ENDIF** 짝이 되는 없이 [IF](../../assembler/masm/if-masm.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ML 오류 메시지](../../assembler/masm/ml-error-messages.md)