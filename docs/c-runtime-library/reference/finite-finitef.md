---
title: "_finite, _finitef | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
dev_langs:
- C++
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
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
ms.openlocfilehash: 90eff10a00ecfdfd772acc7caa624ff35dd392d7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="finite-finitef"></a>_finite, _finitef
부동 소수점 값이 유한인지 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 테스트할 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 둘 다 `_finite` 및 `_finitef` 경우 0이 아닌 값을 반환 인수 *x* 유한;이 있는 경우,-INF < `x` < + INF 합니다. 인수가 무한이거나 NAN이면 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_finite` 및 `_finitef` 함수는 Microsoft 전용입니다. `_finitef` 함수는 x86, ARM 또는 ARM64 플랫폼용으로 컴파일된 경우에만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더(C)|필수 헤더(C++)|  
|--------------|---------------------------|-------------------------------|  
|`_finite`|\<float.h> 또는 \<math.h>|\<float.h>, \<math.h>, \<cfloat> 또는 \<cmath>|  
|`_finitef`|\<math.h>|\<math.h> 또는 \<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)
