---
title: "isnan, _isnan, _isnanf | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs: C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ea88de83d10699c07dd387a616178c0043e925c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf
부동 소수점 값이 NAN(숫자가 아님)인지를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 테스트할 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 C에서는 `x` 인수가 NAN인 경우 `isnan` 매크로와 `_isnan` 및 `_isnanf` 함수가 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다.  
  
 C++에서는 `x` 인수가 NAN인 경우 `isnan` 템플릿 함수가 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 C `isnan` 매크로와 `_isnan` 및 `_isnanf` 함수는 부동 소수점 값 *x*를 테스트하여 *x*가 NAN(숫자가 아님) 값이면 0이 아닌 값을 반환합니다. NAN은 지정된 형식에 대해 부동 소수점 연산의 결과를 IEEE-754 부동 소수점 형식으로 나타낼 수 없는 경우 생성됩니다. 출력에 NAN이 나타나는 방법에 대한 자세한 내용은 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 참조하세요.  
  
 C++로 컴파일된 경우 `isnan` 매크로가 정의되어 있지 않으면 `isnan` 템플릿 함수가 대신 정의됩니다. 이 함수는 정수 대신 `bool` 형식의 값을 반환합니다.  
  
 `_isnan` 및 `_isnanf` 함수는 Microsoft 전용입니다. `_isnanf` 함수는 x64용으로 컴파일된 경우에만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|  
|-------------|---------------------------|-------------------------------|  
|`isnan`, `_isnanf`|\<math.h>|\<math.h> 또는 \<cmath>|  
|`_isnan`|\<float.h>|\<float.h> 또는 \<cfloat>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [_finite, _finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)