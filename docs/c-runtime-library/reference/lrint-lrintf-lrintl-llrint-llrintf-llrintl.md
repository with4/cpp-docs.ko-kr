---
title: "lrint, lrintf, lrintl, llrint, llrintf, llrintl | Microsoft 문서"
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
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
dev_langs:
- C++
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80a331618df913040ea145346299ebd30509ce8e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl
현재 반올림 모드 및 방향을 사용하여 지정된 부동 소수점 값을 가장 가까운 정수 값으로 반올림합니다.  
  
## <a name="syntax"></a>구문  
  
```  
long int lrint(  
   double x  
);  
  
long int lrint(  
   float x  
); //C++ only  
  
long int lrint(  
   long double x  
); //C++ only  
  
long int lrintf(  
   float x  
);  
  
long int lrintl(  
   long double x  
);  
  
long long int llrint(  
   double x  
);  
  
long long int llrint(  
   float x  
); //C++ only  
  
long long int llrint(  
   long double x  
); //C++ only  
  
long long int llrintf(  
   float x  
);  
  
long long int llrintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `x`  
 반올림할 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `x`의 반올림된 정수 값을 반환합니다.  
  
|문제|반환|  
|-----------|------------|  
|`x`가 반환 형식의 범위를 벗어났습니다.<br /><br /> `x` = ±∞<br /><br /> `x` = NaN|FE_INVALID가 발생되고 0이 반환됩니다.|  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 float 및 long double 형식을 사용하는 `lrint` 및 `llrint`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `lrint` 및 `llrint`는 항상 double을 사용합니다.  
  
 `x`가 정수 값에 해당하는 부동 소수점을 나타내지 않는 경우 이러한 함수에서는 FE_INEXACT가 발생합니다.  
  
 **Microsoft 전용**: 결과가 반환 형식의 범위를 벗어났거나 매개 변수가 NaN 또는 무한인 경우 반환 값은 정의된 구현입니다. Microsoft 컴파일러는 0 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`lrint`,                `lrintf`, `lrintl`, `llrint`, `llrintf`, `llrintl`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)