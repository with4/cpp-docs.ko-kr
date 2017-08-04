---
title: "do-while 문 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- do
- while
dev_langs:
- C++
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9ea9e9c4cfdf57709cd125f8269657d37393cc61
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="do-while-statement-c"></a>do-while 문 (C)
`do-while` 문을 사용하면 지정된 식이 false가 될 때까지 문이나 복합 문을 반복할 수 있습니다.  
  
## <a name="syntax"></a>구문  
 *iteration-statement*:  
 **do**  *statement*  **while (**  *expression*  **) ;**  
  
 `do-while` 문의 *expression*은 루프의 본문이 실행된 후 평가됩니다. 따라서 루프의 본문은 항상 한 번 이상 실행됩니다.  
  
 *expression*은 산술 형식이나 포인터 형식이어야 합니다. 다음과 같이 실행됩니다.  
  
1.  문 본문이 실행됩니다.  
  
2.  다음으로, *expression*이 평가됩니다. *expression*이 false인 경우 `do-while` 문이 종료되고 프로그램의 다음 문으로 제어가 전달됩니다. *expression*이 true(0이 아님)인 경우에는 프로세스가 1단계부터 반복됩니다.  
  
 `do-while` 문은 문 본문 내에서 **break**, `goto` 또는 `return` 문이 실행되는 경우에도 종료될 수 있습니다.  
  
 다음은 `do-while` 문의 예제입니다.  
  
```  
do   
{  
    y = f( x );  
    x--;  
} while ( x > 0 );  
```  
  
 이 `do-while` 문에서는 `y = f( x );`의 초기 값과 관계없이 `x--;` 및 `x` 문이 실행됩니다. 그런 다음 `x > 0`이 평가됩니다. `x`가 0보다 크면 문 본문이 다시 실행되고 `x > 0`이 다시 평가됩니다. `x`가 0보다 크게 유지되는 한 문 본문은 반복해서 실행됩니다. `do-while` 문의 실행은 `x`가 0이나 음수가 될 때 종료됩니다. 루프의 본문은 최소한 한 번 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [do-while 문(C++)](../cpp/do-while-statement-cpp.md)
