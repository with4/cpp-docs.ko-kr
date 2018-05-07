---
title: rotate_copy (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::rotate_copy
dev_langs:
- C++
helpviewer_keywords:
- rotate_copy function [STL/CLR]
ms.assetid: ed697552-130f-474f-9ab6-133332bb2587
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e9535280a9e03c6472609069898ad214914330f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="rotatecopy-stlclr"></a>rotate_copy(STL/CLR)
소스 범위 내의 인접한 두 범위의 요소를 교환하고 결과를 대상 범위로 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `rotate_copy`합니다. 자세한 내용은 참조 [rotate_copy](../standard-library/algorithm-functions.md#rotate_copy)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)