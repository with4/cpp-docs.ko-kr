---
title: "numeric(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/numeric>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/numeric> 헤더[STL/CLR]"
  - "<numeric> 헤더[STL/CLR]"
  - "숫자 함수[STL/CLR]"
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# numeric(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

숫자 처리를 위해 제공되는 알고리즘을 수행하는 컨테이너 템플릿 함수들을 정의합니다.  
  
## 구문  
  
```  
#include <cliext/numeric>  
```  
  
## 함수  
  
|Function|설명|  
|--------------|--------|  
|[accumulate](../dotnet/accumulate-stl-clr.md)|연속적인 부분 합계를 계산하여 일부 초기값을 포함한 지정된 범위에 있는 모든 요소의 합계를 계산하거나, 동시에 덧셈보다 지정된 이항 연산을 사용하여 유사하게 얻은 연속 부분 결과들의 결과를 계산합니다.|  
|[adjacent\_difference](../dotnet/adjacent-difference-stl-clr.md)|입력 범위의 각 요소 및 그 이전의 연속적인 차이를 계산하고, 대상 범위에 결과를 출력 또는 차분 연산이 서로에 의해 대체되는 일반화 된 절차, 지정된 이진 연산 결과를 연산합니다.|  
|[inner\_product](../dotnet/inner-product-stl-clr.md)|두 범위 중 element\-wise 결과의 합계를 계산하고 지정된 초기값을 더하거나 덧셈과 2진 연산의 결과기 다른 지정된 2진 연산들로 대체되는 곳의 일반화된 프로시전의 결과를 계산합니다.|  
|[partial\_sum](../dotnet/partial-sum-stl-clr.md)|`i`번째 요소를 통해 첫 번째 요소로부터 입력 범위에 합계를 계산하고 대상 범위의 `i` 번째 요소에서 각각의 덧셈의 결과를 저장하거나 덧셈연산이 다른 지정된 2진 연산으로 대체되는 곳의 일반화된 프로시저의 결과를 계산합니다.|  
  
## 요구 사항  
 **Header:** \<cliext\/numeric\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)