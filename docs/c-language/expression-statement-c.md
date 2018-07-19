---
title: 식 문 (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18d28cdc695ae600616d63575328eeaf171bc28c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385899"
---
# <a name="expression-statement-c"></a>식 문 (C)
식 문이 실행되면 [식 및 할당](../c-language/expressions-and-assignments.md)에 설명된 규칙에 따라 식이 계산됩니다.  
  
## <a name="syntax"></a>구문  
 *expression-statement*:  
 *expression* opt **;**  
  
 식 문의 다음 문은 식 계산의 모든 파생 작업이 완료된 후에 실행됩니다. 빈 식 문을 null 문이라고 합니다. 자세한 내용은 [Null 문](../c-language/null-statement-c.md)을 참조하세요.  
  
 다음 예제에서는 식 문에 대해 설명합니다.  
  
```  
x = ( y + 3 );            /* x is assigned the value of y + 3  */  
x++;                      /* x is incremented                  */  
x = y = 0;                /* Both x and y are initialized to 0 */  
proc( arg1, arg2 );       /* Function call returning void      */  
y = z = ( f( x ) + 3 );   /* A function-call expression        */  
```  
  
 마지막 문인 함수 호출 식에서 함수에서 해당 함수가 반환한 모든 값을 포함하는 식의 값이 3씩 증가한 다음 `y` 및 `z` 변수에 할당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [문](../c-language/statements-c.md)