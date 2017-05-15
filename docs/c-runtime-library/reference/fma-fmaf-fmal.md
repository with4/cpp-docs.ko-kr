---
title: "fma, fmaf, fmal | Microsoft 문서"
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
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 59238cf511be936b0d882c2f00320ee7422904e0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal
두 값을 함께 곱하고, 세 번째 값을 더하고 나서, 결과를 반올림하면 중간 반올림으로 인한 정밀도 손실이 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `x`  
 곱할 첫 번째 값입니다.  
  
 [in] `y`  
 곱할 두 번째 값입니다.  
  
 [in] `z`  
 추가할 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `(x * y) + z`를 반환합니다. 반환 값은 현재 반올림 형식을 사용하여 반올림됩니다.  
  
 그렇지 않으면 다음 값 중 하나를 반환할 수 있습니다.  
  
|문제|반환|  
|-----------|------------|  
|`x` = INFINITY, `y` = 0 또는<br /><br /> `x` = 0, `y` = INFINITY|NaN|  
|`x` 또는 `y` = 정확히 ± INFINITY, `z` = INFINITY(부호가 반대임)|NaN|  
|`x` 또는 `y` = NaN|NaN|  
|not (`x` = 0, `y`= indefinite) 및 `z` = NaN<br /><br /> not (`x`=indefinite, `y`=0) 및 `z` = NaN|NaN|  
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF 또는 ±HUGE_VALL|  
|언더플로 범위 오류|올바른 값, 반올림 후.|  
  
 오류는 [_matherr](../../c-runtime-library/reference/matherr.md)에 지정된 대로 보고됩니다.  
  
## <a name="remarks"></a>설명  
 C + +는 오버 로딩을 허용 하기 때문에 오버 로드를 호출할 수 있습니다 `fma` 사용 하 고 반환 **float** 및 **long double** 형식입니다. C 프로그램에서 `fma` 항상 사용 하 고 반환 된 **double**합니다.  
  
 이 함수는 무한 정밀도에 도달한 것처럼 값을 계산하고 최종 결과를 반올림합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`fma`, `fmaf`, `fmal`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)
