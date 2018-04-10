---
title: inner_product (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::inner_product
dev_langs:
- C++
helpviewer_keywords:
- inner_product function [STL/CLR]
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d61de34fcb029000ac27efcf74bd1321d1b7e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="innerproduct-stlclr"></a>inner_product(STL/CLR)
두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `inner_product`합니다. 자세한 내용은 참조 [inner_product](../standard-library/numeric-functions.md#inner_product)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/숫자 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [numeric(STL/CLR)](../dotnet/numeric-stl-clr.md)