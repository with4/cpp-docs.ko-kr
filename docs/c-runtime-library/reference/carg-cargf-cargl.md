---
title: "carg, cargf, cargl | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- carg
- cargf
- cargl
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
- carg
- cargf
- cargl
- complex/carg
- complex/cargf
- complex/cargl
dev_langs:
- C++
helpviewer_keywords:
- carg function
- cargf function
- cargl function
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
caps.latest.revision: 8
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
ms.openlocfilehash: f4239a5d0834938d80ae2054396e485eef127e4b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="carg-cargf-cargl"></a>carg, cargf, cargl
음의 실수 축을 따라 있는 분기를 사용하여 복소수의 인수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double carg(   
   _Dcomplex z   
);  
float carg(   
   _Fcomplex z   
);  // C++ only  
long double carg(   
   _Lcomplex z   
);  // C++ only  
float cargf(   
   _Fcomplex z   
);  
long double cargl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `z`  
 복소수입니다.  
  
## <a name="return-value"></a>반환 값  
 `z`의 인수(또는 위상)입니다. 결과 간격에 [-π, + π].  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `_Fcomplex` 또는 `_Lcomplex` 값을 사용하고 `float` 또는 `long double` 값을 반환하는 `carg`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `carg`은 항상 `_Dcomplex` 값을 사용하고 `double` 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|C 헤더|C++ 헤더|  
|-------------|--------------|------------------|  
|`carg`,               `cargf`, `cargl`|\<complex.h>|\<ccomplex>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [cabs, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)
