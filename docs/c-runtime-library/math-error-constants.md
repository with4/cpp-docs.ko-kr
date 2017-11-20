---
title: "수학 오류 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
dev_langs: C++
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 003851227d56469436f7c75396803d80052dca15
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="math-error-constants"></a>수학 오류 상수
## <a name="syntax"></a>구문  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>설명  
 런타임 라이브러리의 수학 루틴은 수학 오류 상수를 생성할 수 있습니다.  
  
 이러한 오류는 아래에 설명된 대로 MATH.H에서 정의된 예외 형식에 해당되며 수학 오류가 발생할 때 `_matherr` 함수에 의해 반환됩니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_DOMAIN`|함수에 대한 인수는 함수의 외부 도메인입니다.|  
|`_OVERFLOW`|함수의 반환 형식으로 표현하기에는 결과가 너무 큽니다.|  
|`_PLOSS`|중요 부분 손실이 발생했습니다.|  
|`_SING`|인수 이상: 함수의 인수 값이 잘못되었습니다. 예를 들어 0이 아닌 값이 필요한 함수에 값 0이 전달되었습니다.|  
|`_TLOSS`|중요 전체 손실이 발생했습니다.|  
|`_UNDERFLOW`|결과가 너무 작아 나타낼 수 없습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [_matherr](../c-runtime-library/reference/matherr.md)   
 [전역 상수](../c-runtime-library/global-constants.md)