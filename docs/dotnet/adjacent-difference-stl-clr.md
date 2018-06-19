---
title: adjacent_difference (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::adjacent_difference
dev_langs:
- C++
helpviewer_keywords:
- adjacent_difference function
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fe926d375103ef0f9d1ac5afa56a52742512ace7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103933"
---
# <a name="adjacentdifference-stlclr"></a>adjacent_difference(STL/CLR)
각 요소와 입력 범위의 해당 선행 작업간 연속 차이를 계산하고 결과를 대상 범위로 출력하거나 차이 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `adjacent_difference`합니다. 자세한 내용은 참조 [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/숫자 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [numeric(STL/CLR)](../dotnet/numeric-stl-clr.md)