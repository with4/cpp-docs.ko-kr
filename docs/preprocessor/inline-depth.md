---
title: inline_depth | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3738e1e2217de7e8617f91a36218718cf756ca3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="inlinedepth"></a>inline_depth
함수가 호출 그래프에서 `n`보다 큰 수준으로 인라인 처리되지 않도록 인라인 추론 검색 수준을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>설명  
 이 pragma 제어는 표시 된 함수의 인라이닝을 [인라인](../cpp/inline-functions-cpp.md) 및 [__inline](../cpp/inline-functions-cpp.md) /Ob2 옵션에서 자동으로 인라인 합니다.  
  
 `n`은 0에서 255 사이의 값입니다. 여기서 255는 호출 그래프의 수준이 무제한임을 의미하고 0은 인라인 확장을 금지함을 의미합니다.  `n`이 지정되지 않은 경우 기본값(254)이 사용됩니다.  
  
 **inline_depth** pragma는 일련의 함수 호출을 확장할 수 있는 다시 시도 횟수를 제어 합니다. 예를 들어, 인라인 깊이가 4개이고 A가 B를 호출한 후 B가 C를 호출할 경우 3개의 호출이 모두 인라인 확장됩니다. 그러나 최대 인라인 확장이 2개일 경우 A와 B만 확장되고 C는 함수 호출로 남게 됩니다.  
  
 이 pragma를 사용하려면 /Ob 컴파일러 옵션을 1 또는 2로 설정해야 합니다. 이 pragma를 사용하여 설정한 깊이는 pragma 뒤에 오는 첫 번째 함수 호출에 적용됩니다.  
  
 인라인 깊이는 확장하는 동안 감소할 수 있지만 증가하지 않습니다. 인라인 깊이가 6이 고 확장 하는 동안 전처리기에서 발생 하는 경우는 **inline_depth** pragma 값이 8 깊이를 6으로 유지 됩니다.  
  
 **inline_depth** pragma로 표시 된 함수에 영향을 주지 `__forceinline`합니다.  
  
> [!NOTE]
>  재귀 함수는 최대 16 깊이의 호출까지 인라인을 대체할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_recursion](../preprocessor/inline-recursion.md)