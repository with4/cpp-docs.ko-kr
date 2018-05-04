---
title: return 문 프로그램 종료 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61d09c1b3aaea799c227686436486efa48fc7857
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="return-statement-in-program-termination-c"></a>프로그램 종료 시 return 문 (C++)
발급 한 `return` 에서 문을 **주** 호출 하는 기능적는 **종료** 함수. 다음 예제를 참조하세요.  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **종료** 및 `return` 앞의 예에서 문은 기능적으로 동일 합니다. 그러나 C++에서는 `void`가 아닌 반환 형식을 가지는 함수가 값을 반환해야 합니다. `return` 문을 사용 하면 한 값을 반환할 **주**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 종료](../cpp/program-termination.md)