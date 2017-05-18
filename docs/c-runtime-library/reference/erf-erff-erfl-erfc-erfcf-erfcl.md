---
title: "erf, erff, erfl, erfc, erfcf, erfcl | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 48718acb6ad8773f876251962fd4b643993c27e8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl
값의 오차 함수 또는 보상 오차 함수를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double erf(  
   double x  
);  
float erf(  
   float x  
); // C++ only  
long double erf(  
   long double x  
); // C++ only  
float erff(  
   float x  
);  
long double erfl(  
   long double x  
);  
double erfc(  
   double x  
);  
float erfc(  
   float x  
); // C++ only  
long double erfc(  
   long double x  
); // C++ only  
float erfcf(  
   float x  
);  
long double erfcl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `erf` 함수는 `x`의 가우스 오차 함수를 반환합니다. `erfc` 함수는 `x`의 가우스 보상 오차 함수를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `erf` 함수는 다음과 같이 정의되는 x의 가우스 오차 함수를 계산합니다.  
  
 ![x의 오차 함수](../../c-runtime-library/reference/media/crt_erf_formula.PNG "CRT_erf_formula")  
  
 가우스 보상 오차 함수는-1로 정의 된 erf (x). `erf` 함수는 -1.0~1.0 범위의 값을 반환합니다. 반환되는 오류가 없습니다. `erfc` 함수는 0~2 범위의 값을 반환합니다. `x`가 `erfc`에 대해 너무 크면 `errno` 변수가 `ERANGE`로 설정되어 있습니다.  
  
 C++에서는 오버로드를 허용하므로 `erf` 및 `erfc` 형식을 사용 및 반환하는 `float` 및 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `erf` 및 `erfc`는 항상 `double`을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)
