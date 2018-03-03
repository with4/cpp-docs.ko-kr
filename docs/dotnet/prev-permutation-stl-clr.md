---
title: prev_permutation (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::prev_permutation
dev_langs:
- C++
helpviewer_keywords:
- prev_permutation function [STL/CLR]
ms.assetid: 5294dbe5-1b5f-4369-a764-067dff86d1e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f830d20718e1cab9fd04de1df02b5150cd2d9f02
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="prevpermutation-stlclr"></a>prev_permutation(STL/CLR)
원래 순서 지정을 사전순에 따라 다음으로 큰 순열(있는 경우)로 대체할 수 있도록 범위의 요소 순서를 재정렬합니다. 여기서 다음의 의미는 이진 조건자로 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _BidIt> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `prev_permutation`합니다. 자세한 내용은 참조 [prev_permutation](../standard-library/algorithm-functions.md#prev_permutation)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)