---
title: "csqrt, csqrtf, csqrtl | Microsoft 문서"
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
- csqrt
- csqrtf
- csqrtl
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
- csqrt
- csqrtf
- csqrtl
- complex/csqrt
- complex/csqrtf
- complex/csqrtl
dev_langs:
- C++
helpviewer_keywords:
- csqrt function
- csqrtf function
- csqrtl function
ms.assetid: b65f086b-0f55-4622-a7a3-4e79d9c9c05c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65c295031e2b7d4119c988e4253f34dd7897d30c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="csqrt-csqrtf-csqrtl"></a>csqrt, csqrtf, csqrtl
음의 실수 축을 따라 있는 분기를 사용하여 복소수의 제곱근을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_Dcomplex csqrt(   
   _Dcomplex z   
);  
_Fcomplex csqrt(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex csqrt(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex csqrtf(   
   _Fcomplex z   
);  
_Lcomplex csqrtl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `z`  
 복소수입니다.  
  
## <a name="return-value"></a>반환 값  
 `z`의 제곱근입니다. 결과는 오른쪽 반평면에 있습니다.  
  
|입력|SEH 예외|`_matherr` 예외|  
|-----------|-------------------|--------------------------|  
|± QNAN, IND|없음|_DOMAIN|  
|- ∞|없음|_DOMAIN|  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `csqrt` 및 `_Fcomplex` 값을 사용 및 반환하는 `_Lcomplex`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `csqrt` 는 항상 `_Dcomplex` 값을 사용 및 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|C 헤더|C++ 헤더|  
|-------------|--------------|------------------|  
|`csqrt`,               `csqrtf`, `csqrtl`|\<complex.h>|\<ccomplex>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [ccosh, ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)