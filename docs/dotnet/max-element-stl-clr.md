---
title: max_element (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::max_element
dev_langs: C++
helpviewer_keywords: max_element function [STL/CLR]
ms.assetid: c6274bae-1216-4285-b395-254280253dae
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b80aab744d2212a6710d98c5eb93a6665fa85a2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="maxelement-stlclr"></a>max_element(STL/CLR)
지정된 범위에서 가장 큰 첫 번째 요소를 찾습니다. 정렬 기준은 이진 조건자로 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `max_element`합니다. 자세한 내용은 참조 [max_element](../standard-library/algorithm-functions.md#max_element)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)