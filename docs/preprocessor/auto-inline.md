---
title: auto_inline | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs:
- C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 455d0b78b5807f92d0b675cd695b998c19abba48
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="autoinline"></a>auto_inline
범위 내에서 정의 된 모든 함수는 제외 됩니다. 여기서 **오프** 자동 인라인 확장 후보에서 지정 된 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## <a name="remarks"></a>설명  
 사용 하는 **auto_inline** pragma를 사용 하면 앞과 바로 뒤에 배치 (에 없음) 함수 정의 합니다. pragma가 표시된 후 첫 번째 함수 정의에서 pragma가 적용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)