---
title: unique_copy (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unique_copy
dev_langs:
- C++
helpviewer_keywords:
- unique_copy function [STL/CLR]
ms.assetid: 37aa5b06-42c5-420d-94c5-00f00ad26471
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ab28fbf26151d1ffc1d1c6524b73f325fce94ff2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="uniquecopy-stlclr"></a>unique_copy(STL/CLR)
서로 인접한 중복 요소를 제외하고 소스 범위의 요소를 대상 범위로 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `unique_copy`합니다. 자세한 내용은 참조 [unique_copy](../standard-library/algorithm-functions.md#unique_copy)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)