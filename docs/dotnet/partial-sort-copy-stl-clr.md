---
title: partial_sort_copy (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::partial_sort_copy
dev_langs: C++
helpviewer_keywords: partial_sort_copy function [STL/CLR]
ms.assetid: ed4af83e-7554-4f6d-bf54-c56fa6210fe8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 045cd50d778e515392f02dc9aa17c054617a33b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="partialsortcopy-stlclr"></a>partial_sort_copy(STL/CLR)
소스 범위의 요소를 대상 범위로 복사합니다. 여기서 소스 요소는 지정된 다른 이진 조건자보다 작거나 지정된 다른 이진 조건자로 정렬됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _RanIt> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2);  
template<class _InIt, class _RanIt, class _Pr> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `partial_sort_copy`합니다. 자세한 내용은 참조 [partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)