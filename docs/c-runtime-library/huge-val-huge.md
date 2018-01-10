---
title: "HUGE_VAL, _HUGE | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _HUGE
apilocation: msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs: C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27fbb0ae4f8bbe658c37c0e979ea97a4dcec2fb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE
## <a name="syntax"></a>구문  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>설명  
 `HUGE_VAL`은 표현할 수 있는 가장 큰 double 값입니다. 오류가 발생하면 여러 런타임 수학 함수에 의해 이 값이 반환됩니다. 일부 함수의 경우 -`HUGE_VAL`가 반환됩니다. `HUGE_VAL`이 `_HUGE`로 정의되지만 런타임 수학 함수는 `HUGE_VAL`을 반환합니다. 또한 일관성을 위해 코드에 `HUGE_VAL`를 사용해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)