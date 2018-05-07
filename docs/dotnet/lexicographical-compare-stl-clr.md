---
title: lexicographical_compare (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::lexicographical_compare
dev_langs:
- C++
helpviewer_keywords:
- lexicographical_compare function [STL/CLR]
ms.assetid: 9ec217f3-5523-4f90-a0cc-8fb7dbe4946b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49d5243b729e8e1beeeb11536a80bb6937d25879
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="lexicographicalcompare-stlclr"></a>lexicographical_compare(STL/CLR)
두 시퀀스를 요소별로 비교하여 둘 중 작은 것을 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `lexicographical_compare`합니다. 자세한 내용은 참조 [lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)