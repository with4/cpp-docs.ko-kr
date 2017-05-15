---
title: "logb, logbf, logbl, _logb, _logbf | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
dev_langs:
- C++
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5c5c07c13008d9abb5163c8e309d72848388341c
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf
부동 소수점 인수의 지수 값을 추출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 x  
 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `logb`는 `x`의 비편향 지수 값을 부동 소수점 값으로 표현된 부호 있는 정수로 반환합니다.  
  
## <a name="remarks"></a>설명  
 `logb` 함수는 `x`가 무한 범위로 표현된 것처럼 부동 소수점 인수 `x`의 지수 값을 추출합니다. `x` 인수는 비정규화된 경우 정규화된 것처럼 처리됩니다.  
  
 C++에서는 오버로드를 허용하므로 `logb` 또는 `float` 값을 사용 및 반환하는 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `logb`는 항상 `double`을 사용 및 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|-----------|-------------------|-----------------------|  
|± QNAN,IND|없음|_DOMAIN|  
|± 0|ZERODIVIDE|_SING|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_logb`|\<float.h>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)
