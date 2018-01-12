---
title: "return 문 프로그램 종료 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9a9e97c0ee52094cd3f0ccbb36c0da8b3b04c630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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