---
title: "return 문 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- return_cpp
dev_langs:
- C++
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d6857983412b2037b8958c2b1a0bee9d9dda053
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="return-statement-c"></a>return 문 (C++)
함수 실행을 종료하고 컨트롤을 호출 함수(또는 `main` 함수에서 컨트롤을 이전하는 경우 운영 체제로)로 반환합니다. 호출 바로 다음 지점의 호출 함수에서 실행을 다시 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
return [expression];  
```  
  
## <a name="remarks"></a>설명  
 `expression` 절(있는 경우)은 초기화가 수행되고 있었던 것처럼 함수 선언에 지정된 형식으로 변환됩니다. 식의 형식에서 함수의 `return` 형식으로의 변환은 임시 개체를 만들 수 있습니다. 임시 개체를 만드는 방법 및 시기에 대 한 자세한 내용은 참조 [임시 개체](../cpp/temporary-objects.md)합니다.  
  
 `expression` 절 값이 호출 함수에 반환됩니다. 식을 생략하면 함수의 반환 값이 정의되지 않습니다. 생성자 및 소멸자 및 유형의 함수 `void`에 식을 지정할 수 없습니다는 `return` 문. 다른 모든 형식의 함수는 `return` 문에서 식을 지정해야 합니다.  
  
 제어 흐름에서 함수 정의를 포함하는 블록을 종료하면, 식이 없는 `return` 문이 실행되는 경우와 동일해 집니다. 값을 반환할 때 선언되는 함수에는 올바르지 않습니다.  
  
 함수에는 `return` 문을 원하는 만큼 포함할 수 있습니다.  
  
 다음 예제에서는 두 정수 중 가장 큰 정수를 얻기 위해 `return` 문이 있는 식을 사용합니다.  
  
## <a name="example"></a>예  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [점프 문](../cpp/jump-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)