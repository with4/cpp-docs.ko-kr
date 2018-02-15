---
title: "ML 심각한 오류 A1011 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3a614bc56c76b220eeeb73ce2cc7e90a9ca9b8e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-fatal-error-a1011"></a>ML 심각한 오류 A1011
**지시어는 제어 블록에 있어야 합니다.**  
  
 어셈블러 여기서 없어야 하는 높은 수준의 지시문을 찾을 수 있습니다. 지시문은 다음 중 하나를 찾을 수 있습니다.  
  
-   [. 다른](../../assembler/masm/dot-else.md) 없이 [합니다. IF](../../assembler/masm/dot-if.md)  
  
-   [. ENDIF](../../assembler/masm/dot-endif.md) 없이 [합니다. IF](../../assembler/masm/dot-if.md)  
  
-   [. ENDW](../../assembler/masm/dot-endw.md) 없이 [합니다. WHILE](../../assembler/masm/dot-while.md)  
  
-   [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) 없이 [합니다. 반복](../../assembler/masm/dot-repeat.md)  
  
-   [. 계속](../../assembler/masm/dot-continue.md) 없이 [합니다. 반면](../../assembler/masm/dot-while.md) 또는 [합니다. 반복](../../assembler/masm/dot-repeat.md)  
  
-   [. 중단](../../assembler/masm/dot-break.md) 없이 [합니다. 반면](../../assembler/masm/dot-while.md) 또는 [합니다. 반복](../../assembler/masm/dot-repeat.md)  
  
-   [. 다른](../../assembler/masm/dot-else.md) 다음 `.ELSE`  
  
## <a name="see-also"></a>참고 항목  
 [ML 오류 메시지](../../assembler/masm/ml-error-messages.md)