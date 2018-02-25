---
title: inline_recursion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f3e4ef784d2fcb9ec076d9f8a7c87ffee1d5800
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="inlinerecursion"></a>inline_recursion
직접 또는 상호 재귀 함수 호출의 인라인 확장을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## <a name="remarks"></a>설명  
 로 표시 된 제어 기능 하려면이 pragma를 사용 하 여 [인라인](../cpp/inline-functions-cpp.md) 및 [__inline](../cpp/inline-functions-cpp.md) 함수나 컴파일러가 /Ob2 옵션에서 자동으로 확장 합니다. 이 pragma 사용 하려면 필요는 [/Ob](../build/reference/ob-inline-function-expansion.md) 1 또는 2 컴파일러 옵션 설정입니다. `inline_recursion`의 기본 상태는 off입니다. 이 pragma는 pragma가 표시된 후 첫 번째 함수에서 적용되며 함수의 정의에는 영향을 미치지 않습니다.  
  
 `inline_recursion` pragma는 재귀 함수가 확장되는 방식을 제어합니다. `inline_recursion`이 off인 경우 인라인 함수가 자신을 호출하면(직접적 또는 간접적으로) 함수는 한 번만 확장됩니다. 경우 `inline_recursion` 켜져 함수로 설정 된 값에 도달할 때까지 여러 번 확장 됩니다는 [inline_depth](../preprocessor/inline-depth.md) pragma에 의해 정의 된 재귀 함수의 기본값은 `inline_depth` pragma, 또는 용량 한도 .  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_depth](../preprocessor/inline-depth.md)   
 [/Ob(인라인 함수 확장)](../build/reference/ob-inline-function-expansion.md)