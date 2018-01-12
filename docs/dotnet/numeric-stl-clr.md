---
title: numeric (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: <cliext/numeric>
dev_langs: C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cdf9ccb65299af688fde2fbff7b3d6cedad6de96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="numeric-stlclr"></a>numeric(STL/CLR)
숫자 처리를 위해 제공 하는 알고리즘을 수행 하는 컨테이너 템플릿 함수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <cliext/numeric>  
```  
  
## <a name="functions"></a>함수  
  
|함수|설명|  
|--------------|-----------------|  
|[accumulate(STL/CLR)](../dotnet/accumulate-stl-clr.md)|연속적 부분 합계를 계산하여 일부 초기값을 비롯한 지정된 범위 내 모든 요소의 합계를 계산하거나, 합계 대신 지정된 이진 연산을 사용하여 유사하게 구한 연속적 부분 결과의 결과를 계산합니다.|  
|[adjacent_difference(STL/CLR)](../dotnet/adjacent-difference-stl-clr.md)|각 요소와 입력 범위의 해당 선행 작업간 연속 차이를 계산하고 결과를 대상 범위로 출력하거나 차이 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.|  
|[inner_product(STL/CLR)](../dotnet/inner-product-stl-clr.md)|두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.|  
|[partial_sum(STL/CLR)](../dotnet/partial-sum-stl-clr.md)|일련의 첫 번째 요소를 통해 입력 범위의 합계를 계산 합니다.는 `i`th 요소 각 합계의 결과 저장 하 고 `i`번째 요소를 대상 범위로 하거나 일반화 된 절차 결과를 계산 합니다. 여기서 합 연산을 지정 된 다른 이진 연산으로 대체 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/숫자 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)