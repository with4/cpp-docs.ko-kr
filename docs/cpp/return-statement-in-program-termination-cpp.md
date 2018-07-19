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
ms.openlocfilehash: eb594eb10e8068d5f5b3ed124d5e77b48ced728e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943147"
---
# <a name="return-statement-in-program-termination-c"></a>프로그램 종료 시 return 문 (C++)
발급을 `return` 에서 문을 **주** 기능적으로 호출 합니다 **종료** 함수. 다음 예제를 참조하세요.  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 합니다 **종료** 하 고 **반환** 문 앞의 예제에서 기능적으로 동일 합니다. 그러나 c + +에서는 함수를 반환 형식 이외의 **void** 값을 반환 합니다. 합니다 **반환** 문을 사용 하면에서 값을 반환 하려면 `main`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 종료](../cpp/program-termination.md)