---
title: set_intersection (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set_intersection
dev_langs:
- C++
helpviewer_keywords:
- set_intersection function [STL/CLR]
ms.assetid: 8a799b20-55a5-4fba-a9c1-a48597cbdae6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3b94978b2a630a6c54b8252b64b1c67c0110a50e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="setintersection-stlclr"></a>set_intersection(STL/CLR)
정렬된 두 소스 범위에 속하는 모든 요소를 정렬된 단일 대상 범위로 결합합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `set_intersection`합니다. 자세한 내용은 참조 [set_intersection](../standard-library/algorithm-functions.md#set_intersection)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)