---
title: (STL/CLR)를 생성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::generate
dev_langs:
- C++
helpviewer_keywords:
- generate function [STL/CLR]
ms.assetid: 970f209f-31db-47c4-a0bb-4c3e579adb52
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e5e5ebe9b6037de30bb95d578072167c64521849
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="generate-stlclr"></a>generate(STL/CLR)
범위에 있는 각 요소에 함수 개체에 의해 생성된 값을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _FwdIt, class _Fn0> inline  
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 함수 동일 하 게 동작 `generate`합니다. 자세한 내용은 참조 [생성](../standard-library/algorithm-functions.md#generate)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<알고리즘 cliext/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)