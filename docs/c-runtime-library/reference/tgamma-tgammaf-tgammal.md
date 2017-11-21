---
title: tgamma, tgammaf, tgammal | Microsoft Docs
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
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs: C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 24c4cc90ed77a57ad053f5608ad5eaf2d1ed62f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal
지정된 값의 감마 함수를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `x`  
 감마를 찾을 값입니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되면 `x`의 감마를 반환합니다.  
  
 데이터 형식에 비해 `x`의 크기가 너무 크거나 너무 작으면 범위 오류가 발생할 수 있습니다. `x` <=0인 경우 도메인 오류 또는 범위 오류가 발생할 수 있습니다.  
  
|문제|반환|  
|-----------|------------|  
|x = ±0|±INFINITY|  
|x = 음의 정수|NaN|  
|x = -INFINITY|NaN|  
|x = +INFINITY|+INFINITY|  
|x = NaN|NaN|  
|도메인 오류|NaN|  
|극 오류|±HUGE_VAL, ±HUGE_VALF 또는 ±HUGE_VALL|  
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF 또는 ±HUGE_VALL|  
|언더플로 범위 오류|반올림 후의 올바른 값|  
  
 오류는 [_matherr](../../c-runtime-library/reference/matherr.md)에 지정된 대로 보고됩니다.  
  
## <a name="remarks"></a>설명  
 C++는 오버로드를 허용하기 때문에 float 및 long double 형식을 사용하고 반환하는 tgamma의 오버로드를 호출할 수 있습니다. C 프로그램에서 tgamma는 항상 double을 사용하고 반환합니다.  
  
 X가 자연수인 경우 이 함수는 (x-1)의 계승을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`tgamma`,                `tgammaf`,  `tgammal`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma, lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)