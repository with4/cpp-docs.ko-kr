---
title: "부동 소수점 숫자의 정밀도가 떨어지는 이유 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DBL_EPSILON 상수"
  - "부동 소수점 숫자, 전체 자릿수"
  - "FLT_EPSILON 상수"
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 부동 소수점 숫자의 정밀도가 떨어지는 이유
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적으로 부동 소수점 십진수 값은 정확히 이진수로 나타내지 못합니다.  이는 CPU에서 부동 소수점 데이터를 나타내는 방식 때문입니다.  따라서 정밀도가 약간 떨어질 수 있으며 부동 소수점 연산에서 예상치 않은 결과가 산출되는 경우도 있습니다.  
  
 그 원인은 다음 중 한 가지입니다.  
  
-   십진수를 이진수로 정확하게 표시할 수 없습니다.  
  
-   사용된 숫자의 형식이 일치하지 않습니다\(예: float와 double\).  
  
 문제를 해결하려면 결과 값이 필요한 값보다 큰지 작은지 확인하거나 정밀도를 유지하는 BCD\(Binary Coded Decimal\) 라이브러리를 사용합니다.  
  
 부동 소수점 값을 이진수로 표현하면 부동 소수점 계산의 정밀도와 정확도에 영향을 미칩니다.  Microsoft Visual C\+\+는 [IEEE 부동 소수점 형식](../../build/reference/ieee-floating-point-representation.md)을 사용합니다.  
  
## 예제  
  
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
  
  **서로 같은 것이 아닙니다\!  c 값은 2.4679999352 또는 2.468000입니다.**    
## 설명  
 EPSILON의 경우에는 float에 대해 1.192092896e\-07F로 정의된 상수 FLT\_EPSILON을 사용하거나 double에 대해 2.2204460492503131e\-016로 정의된 DBL\_EPSILON을 사용할 수 있습니다.  이 두 상수에 대해 float.h를 포함해야 합니다.  이 두 상수는 가장 작은 양수 x\(예: x\+1.0은 1.0과 같지 않음\)로 정의됩니다.  이 수는 매우 작은 수이므로 큰 수를 계산하는 경우에는 사용자 정의 허용 오차를 채택해야 합니다.  
  
## 참고 항목  
 [코드 최적화](../../build/reference/optimizing-your-code.md)