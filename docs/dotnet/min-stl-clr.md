---
title: min (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::min
dev_langs:
- C++
helpviewer_keywords:
- min function [STL/CLR]
ms.assetid: 7a2c82d1-424c-48a9-a944-adcf95511aef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5449af49537a2a7633048415d06217edbc64783d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="min-stlclr"></a>min(STL/CLR)
두 개체를 비교하고 둘 중 작은 개체를 반환합니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _Ty> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `min`합니다. 자세한 내용은 참조 [min](../standard-library/algorithm-functions.md#min)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)