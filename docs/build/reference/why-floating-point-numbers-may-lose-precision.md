---
title: "부동 소수점 숫자의 정밀도 떨어지는 이유 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 371aad5dc573a13ca834d8d6d9667a43bb40324e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>부동 소수점 숫자의 정밀도가 떨어지는 이유
부동 소수점 10 진수 값 일반적으로 필요는 없습니다는 정확한 이진 표현입니다. 이 CPU에서 부동 소수점 데이터를 나타내는 하는 방식 때문입니다. 이러한 이유로, 자릿수 손실이 발생할 수 있습니다 및 부동 소수점 연산에 예기치 않은 결과가 발생할 수 있습니다.  
  
 이 동작은 다음 중 하나입니다.  
  
-   10 진수 숫자의 이진 표현 정확한 아닐 수 있습니다.  
  
-   사용 되는 숫자 (예: float 및 double 혼합) 일치 형식이 일치 하지가 않습니다.  
  
 문제를 해결 하려면 않은지 확인 하거나 값이 크면 보다 적은 필요한 대부분의 프로그래머가 쉽게 또는 가져오고 정밀도 유지 관리 Binary Coded Decimal (BCD) 라이브러리를 사용 합니다.  
  
 부동 소수점 값의 이진 표현 전체 자릿수와 부동 소수점 계산의 정확도 영향을 줍니다. Microsoft Visual c + +를 사용 하 여 [IEEE 부동 소수점 형식](../../build/reference/ieee-floating-point-representation.md)합니다.  
  
## <a name="example"></a>예  
  
```  
// Floating-point_number_precision.c  
// Compile options needed: none. Value of c is printed with a decimal   
// point precision of 10 and 6 (printf rounded value by default) to   
// show the difference  
#include <stdio.h>  
  
#define EPSILON 0.0001   // Define your own tolerance  
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))  
  
int main() {  
   float a, b, c;  
  
   a = 1.345f;  
   b = 1.123f;  
   c = a + b;  
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result  
   if (c == 2.468)            // Comment this line for correct result  
      printf_s("They are equal.\n");  
   else  
      printf_s("They are not equal! The value of c is %13.10f "  
                "or %f",c,c);  
}  
```  
  
```Output  
They are not equal! The value of c is  2.4679999352 or 2.468000  
```  
  
## <a name="comments"></a>설명  
 EPSILON에 FLT_EPSILON 1.192092896e로 float에 대 한 정의 된 상수를 사용할 수 있습니다-07F, DBL_EPSILON 2.2204460492503131e로 더블에 대해 정의 된 또는-016 합니다. 이러한 상수에 대 한 float.h를 포함 해야 합니다. 이러한 상수 정의 된 가장 작은 양수 x 번호, x + 1.0 되어 서 1.0과 같지 않음. 아주 작은 숫자 이기 때문에 매우 큰 숫자를 포함 하는 계산에 대 한 사용자 정의 허용 오차를 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 최적화](../../build/reference/optimizing-your-code.md)