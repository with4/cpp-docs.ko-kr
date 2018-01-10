---
title: "ceil, ceilf, ceill | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ceilf
- ceil
- ceill
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
- ntdll.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ceil
- ceilf
- ceill
dev_langs: C++
helpviewer_keywords:
- calculating value ceilings
- ceill function
- ceil function
- ceilf function
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4831b9f6f046dbc1a5d337f22e6be3dc3f4a5662
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ceil-ceilf-ceill"></a>ceil, ceilf, ceill
값의 최대 한계를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `ceil` 함수는 `x`보다 크거나 같은 가장 작은 정수를 나타내는 부동 소수점 값을 반환합니다. 반환되는 오류가 없습니다.  
  
|입력|SEH 예외|Matherr 예외|  
|-----------|-------------------|-----------------------|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
  
 `ceil`에는 SSE2(스트리밍 SIMD 확장 2)를 사용하는 구현이 포함됩니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `ceil`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `ceil`은 항상 Double을 사용하고 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`ceil`, `ceilf`, `ceill`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
 [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)
