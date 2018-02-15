---
title: "cabs, cabsf, cabsl | Microsoft 문서"
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
- cabs
- cabsf
- cabsl
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
- cabs
- cabsf
- cabsl
- complex/cabs
- complex/cabsf
- complex/cabsl
dev_langs:
- C++
helpviewer_keywords:
- cabs function
- cabsf function
- cabsl function
ms.assetid: 6b8eb453-cc8f-4972-bebf-351cbdfdfc15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5e2a256b0120a42ef5963b3989b64edd5d95fca
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cabs-cabsf-cabsl"></a>cabs, cabsf, cabsl
복소수의 절대값을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double cabs(   
   _Dcomplex z   
);  
float cabs(   
   _Fcomplex z   
);  // C++ only  
long double cabs(   
   _Lcomplex z   
);  // C++ only  
float cabsf(   
   _Fcomplex z   
);  
long double cabsl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `z`  
 복소수입니다.  
  
## <a name="return-value"></a>반환 값  
 `z`의 절대값입니다.  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `_Fcomplex` 또는 `_Lcomplex` 값을 사용하고 `float` 또는 `long double` 값을 반환하는 `cabs`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `cabs`은 항상 `_Dcomplex` 값을 사용하고 `double` 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|C 헤더|C++ 헤더|  
|-------------|--------------|------------------|  
|`cabs`,               `cabsf`, `cabsl`|\<complex.h>|\<ccomplex>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [carg, cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)