---
title: break 문 (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- break
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 194e4c836f0423e20bb747cc6c3b06645c38a5fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381352"
---
# <a name="break-statement-c"></a>break 문 (C)
`break` 문은 해당 문이 배치된 지점에서 가장 가까이에 있는 `do`, `for`, `switch` 또는 `while` 문의 실행을 종료합니다. 제어는 종료된 문 뒤의 문으로 전달됩니다.  
  
## <a name="syntax"></a>구문  
 *점프 문*:  
 `break;`  
  
 `break` 문은 `switch` 문 내의 특정 경우의 처리를 종료하는 데 자주 사용됩니다. 닫힌 반복문 또는 `switch` 문이 없으면 오류가 발생합니다.  
  
 중첩된 문 내의 `break` 문은 해당 문을 둘러싼 `do`, `for`, `switch` 또는 `while` 문만을 종료합니다. `return` 또는 `goto` 문을 사용하여 제어를 중첩된 구조 외부의 다른 지점으로 전달할 수도 있습니다.  
  
 이 예제에서는 `break` 문에 대해 설명합니다.  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## <a name="see-also"></a>참고 항목  
 [break 문](../cpp/break-statement-cpp.md)