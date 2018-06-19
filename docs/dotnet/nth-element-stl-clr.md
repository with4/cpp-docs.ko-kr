---
title: nth_element (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::nth_element
dev_langs:
- C++
helpviewer_keywords:
- nth_element function [STL/CLR]
ms.assetid: 19fc1695-62a9-4f85-9920-d153c1c6481f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4517ca62c7f7e376a13f2b3e02488d6c0256031a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132897"
---
# <a name="nthelement-stlclr"></a>nth_element(STL/CLR)
정확 하 게 찾습니다 요소의 범위를 분할 된 `n`th 요소 범위에서 시퀀스의 앞에 있는 모든 요소 보다 작거나 같은 다음 시퀀스의 모든 요소가 하는 것 보다 크거나 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _RanIt> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `nth_element`합니다. 자세한 내용은 참조 [nth_element](../standard-library/algorithm-functions.md#nth_element)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)