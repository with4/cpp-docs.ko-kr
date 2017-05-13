---
title: "clog, clogf, clogl | Microsoft 문서"
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
- clog
- clogf
- clogl
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
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
dev_langs:
- C++
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: 9
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
ms.openlocfilehash: 2778a27aa2859d7abb5f247e71397af6aa8b0da6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="clog-clogf-clogl"></a>clog, clogf, clogl
음의 실수 축을 따라 분기를 사용하여 복소수의 자연 로그를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `z`  
 로그의 밑입니다.  
  
## <a name="return-value"></a>반환 값  
 `z`의 자연 로그입니다. 결과 실제 축을 따라 및 간격에서 경계 수 없습니다. [-iπ, + iπ] 허수 축을 따라 합니다.  
  
 가능한 반환 값은 다음과 같습니다.  
  
|z 매개 변수|반환 값|  
|-----------------|------------------|  
|양수|z의 밑이 10인 로그|  
|0|- ∞|  
|음수|NaN|  
|NaN|NaN|  
|+ ∞|+ ∞|  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `clog` 및 `_Fcomplex` 값을 사용 및 반환하는 `_Lcomplex`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `clog` 는 항상 `_Dcomplex` 값을 사용 및 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|C 헤더|C++ 헤더|  
|-------------|--------------|------------------|  
|`clog`,               `clogf`, `clogl`|\<complex.h>|\<ccomplex>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)
