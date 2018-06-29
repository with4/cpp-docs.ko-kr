---
title: numeric (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/numeric>
- cliext::accumulate
- cliext::adjacent_difference
- cliext::inner_product
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
- accumulate function [STL/CLR]
- adjacent_difference function [STL/CLR]
- inner_product function [STL/CLR]
- partial_sum function [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f8d470928cb4cbc1625ad439efe75b97f2bb1bd7
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079044"
---
# <a name="numeric-stlclr"></a>numeric(STL/CLR)
숫자 처리를 위해 제공 하는 알고리즘을 수행 하는 컨테이너 템플릿 함수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <cliext/numeric>  
```  

## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/숫자 >  
  
 **Namespace:** cliext  
  
## <a name="declarations"></a>선언  
  
|기능|설명|  
|--------------|-----------------|  
|[accumulate(STL/CLR)](#accumulate)|연속적 부분 합계를 계산하여 일부 초기값을 비롯한 지정된 범위 내 모든 요소의 합계를 계산하거나, 합계 대신 지정된 이진 연산을 사용하여 유사하게 구한 연속적 부분 결과의 결과를 계산합니다.|  
|[adjacent_difference(STL/CLR)](#adjacent_difference)|각 요소와 입력 범위의 해당 선행 작업간 연속 차이를 계산하고 결과를 대상 범위로 출력하거나 차이 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.|  
|[inner_product(STL/CLR)](#inner_product)|두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.|  
|[partial_sum(STL/CLR)](#partial_sum)|일련의 첫 번째 요소를 통해 입력 범위의 합계를 계산 합니다.는 `i`th 요소 각 합계의 결과 저장 하 고 `i`번째 요소를 대상 범위로 하거나 일반화 된 절차 결과를 계산 합니다. 여기서 합 연산을 지정 된 다른 이진 연산으로 대체 됩니다.|  
 
## <a name="members"></a>멤버

## <a name="accumulate"></a> accumulate (STL/CLR)
연속적 부분 합계를 계산하여 일부 초기값을 비롯한 지정된 범위 내 모든 요소의 합계를 계산하거나, 합계 대신 지정된 이진 연산을 사용하여 유사하게 구한 연속적 부분 결과의 결과를 계산합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `accumulate`합니다. 자세한 내용은 참조 [누적](../standard-library/numeric-functions.md#accumulate)합니다.  

## <a name="adjacent_difference"></a> adjacent_difference (STL/CLR)
각 요소와 입력 범위의 해당 선행 작업간 연속 차이를 계산하고 결과를 대상 범위로 출력하거나 차이 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `adjacent_difference`합니다. 자세한 내용은 참조 [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)합니다.  

## <a name="inner_product"></a> inner_product (STL/CLR)
두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.  
  
###<a name="syntax"></a>구문  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
### <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `inner_product`합니다. 자세한 내용은 참조 [inner_product](../standard-library/numeric-functions.md#inner_product)합니다.

## <a name="partial_sum"></a> partial_sum (STL/CLR)
일련의 첫 번째 요소를 통해 입력 범위의 합계를 계산 합니다.는 `i`th 요소 각 합계의 결과 저장 하 고 `i`번째 요소를 대상 범위로 하거나 일반화 된 절차 결과를 계산 합니다. 여기서 합 연산을 지정 된 다른 이진 연산으로 대체 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `partial_sum`합니다. 자세한 내용은 참조 [partial_sum](../standard-library/numeric-functions.md#partial_sum)합니다.  
    