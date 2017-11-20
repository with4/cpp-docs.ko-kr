---
title: "lgamma, lgammaf, lgammal | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- lgamma
- lgammaf
- lgammal
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
dev_langs: C++
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: afc048d131bd75a9645c045b3bceae90344c07eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal
지정된 값에 대한 감마 함수 절대 값의 자연 로그를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `x`  
 계산할 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `x.`에 대한 감마 함수 절대 값의 자연 로그를 반환합니다.  
  
|문제|반환|  
|-----------|------------|  
|`x` = NaN|NaN|  
|`x` = ±0|+INFINITY|  
|`x`= 음의 정수|+INFINITY|  
|±INFINITY|+INFINITY|  
|극 오류|+HUGE_VAL, +HUGE_VALF 또는 +HUGE_VALL|  
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF 또는 ±HUGE_VALL|  
  
 오류는 [_matherr](../../c-runtime-library/reference/matherr.md)에 지정된 대로 보고됩니다.  
  
## <a name="remarks"></a>설명  
 C++는 오버로드를 허용하기 때문에 float 및 long double 형식을 사용하고 반환하는 `lgamma`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `lgamma`는 항상 Double을 사용하고 반환합니다.  
  
 X가 유리수인 경우 이 함수는 (`x`-1)의 계승의 로그를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`lgamma`,                `lgammaf`,  `lgammal`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tgamma, tgammaf, tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)