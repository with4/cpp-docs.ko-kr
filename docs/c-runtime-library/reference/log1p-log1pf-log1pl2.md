---
title: "log1p, log1pf, log1pl2 | Microsoft 문서"
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
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: 7
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
ms.openlocfilehash: 99525c8b711d0774fa2b3132505a2cdbb21d5569
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl
1을 더한 지정된 값의 자연 로그를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 부동 소수점 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 (`x`+1)의 자연 로그(밑 e)를 반환합니다.  
  
 그렇지 않으면 다음 값 중 하나를 반환할 수 있습니다.  
  
|입력|결과|SEH 예외|errno|  
|-----------|------------|-------------------|-----------|  
|+inf|+inf|||  
|Denormals|입력과 동일함|UNDERFLOW||  
|±0|입력과 동일함|||  
|-1|-inf|DIVBYZERO|ERANGE|  
|< -1|nan|INVALID|EDOM|  
|-inf|nan|INVALID|EDOM|  
|±SNaN|입력과 동일함|INVALID||  
|±QNaN, 무한|입력과 동일함|||  
  
 `x` = -1이면 `errno` 값은 ERANGE로 설정됩니다. `errno` 값으로 설정 되어 EDOM `x` <-1입니다.  
  
## <a name="remarks"></a>설명  
 x가 0에 가까우면 `log1p` 함수는 log(`x`+1)를 사용할 때보다 더 정확할 수 있습니다.  
  
 C++는 오버로드를 허용하기 때문에 float 및 long double 형식을 사용하고 반환하는 `log1p`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `log1p`는 항상 Double을 사용하고 반환합니다.  
  
 `x`가 자연수인 경우 이 함수는 (`x`-1)의 계승의 로그를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`log1p`,                `log1pf`,  `log1pl`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)
