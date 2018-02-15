---
title: fmin, fminf, fminl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d90de1e734b2d2da4770c7a5ad85a5ee60a15408
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl
지정된 두 값 중 더 작은 값을 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 비교할 첫 번째 값입니다.  
  
 `y`  
 비교할 두 번째 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `x` 또는 `y` 중 더 작은 값을 반환합니다.  
  
|입력|결과|  
|-----------|------------|  
|`x` = NaN|`y`|  
|`y` = NaN|`x`|  
|`x` 및 `y` = NaN|NaN|  
  
 이 함수는 [_matherr](../../c-runtime-library/reference/matherr.md)를 호출하거나, 부동 소수점 예외를 발생시키거나, `errno` 값을 변경하지 않습니다.  
  
## <a name="remarks"></a>설명  
 C++는 오버로드를 허용하기 때문에 float 및 long double 형식을 사용하고 반환하는 `fmin`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `fmin`는 항상 double을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`fmin`, `fminf`, `fminl`|C: \<math.h><br />C++: \<math.h> 또는 \<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)  