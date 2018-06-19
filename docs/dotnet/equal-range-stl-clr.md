---
title: equal_range (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range function [STL/CLR]
ms.assetid: 1b2e76c3-6b52-486d-9785-2639b54277fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9001d4b39b1b20e2caa7b5d81ac3b06d42042071
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105870"
---
# <a name="equalrange-stlclr"></a>equal_range(STL/CLR)
정렬된 범위에서 위치의 쌍을 찾습니다. 첫 번째는 지정된 요소의 위치보다 작거나 같으며 두 번째는 요소의 위치보다 큽니다. 여기서 시퀀스의 위치를 정하는 데 사용된 동등성 또는 순서 지정의 의미는 이진 조건자로 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `equal_range`합니다. 자세한 내용은 참조 [equal_range](../standard-library/algorithm-functions.md#equal_range)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)