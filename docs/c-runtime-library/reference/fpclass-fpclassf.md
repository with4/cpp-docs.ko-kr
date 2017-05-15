---
title: "_fpclass, _fpclassf | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
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
ms.openlocfilehash: 9f061841ea6f4050945caeb2cacb9acfdce77c44
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf
인수의 부동 소수점 분류를 나타내는 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 테스트할 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `_fpclass` 및 `_fpclassf` 함수는 인수 `x`의 부동 소수점 분류를 나타내는 정수 값을 반환합니다. 분류는 \<float.h>에 정의된 다음 값 중 하나를 가질 수 있습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|신호 NaN|  
|`_FPCLASS_QNAN`|자동 NaN|  
|`_FPCLASS_NINF`|음의 무한대 (– INF)|  
|`_FPCLASS_NN`|정규화된 0이 아닌 음수 값|  
|`_FPCLASS_ND`|비정규화된 음수|  
|`_FPCLASS_NZ`|음수 0 (-0)|  
|`_FPCLASS_PZ`|양수 0(+0)|  
|`_FPCLASS_PD`|비정규화된 양수|  
|`_FPCLASS_PN`|정규화된 0이 아닌 양수 값|  
|`_FPCLASS_PINF`|양수 무한대(+INF)|  
  
## <a name="remarks"></a>설명  
 `_fpclass` 및 `_fpclassf` 함수는 Microsoft 전용입니다. [fpclassify](../../c-runtime-library/reference/fpclassify.md)와 비슷하지만 인수에 대한 더 자세한 정보를 반환합니다. `_fpclassf` 함수는 x64 플랫폼용으로 컴파일된 경우에만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_fpclass`|\<float.h>|  
  
 호환성 및 규칙에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)
