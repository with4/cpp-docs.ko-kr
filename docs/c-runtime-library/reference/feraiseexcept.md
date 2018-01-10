---
title: "feraiseexcept | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feraiseexcept
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
apitype: HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
dev_langs: C++
helpviewer_keywords: feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ab77da8cee422bab618dc8737ad254b65301ffd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="feraiseexcept"></a>feraiseexcept
지정된 부동 소수점 예외를 발생시킵니다.  
  
## <a name="syntax"></a>구문  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `excepts`  
 발생시킬 부동 소수점 예외입니다.  
  
## <a name="return-value"></a>반환 값  
 모든 지정된 예외가 성공적으로 발생하면 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `feraiseexcept` 함수는 `excepts`를 통해 지정한 부동 소수점 예외를 발생시키려고 합니다.   `feraiseexcept` 함수는 \<fenv.h>에 정의된 다음 예외 매크로를 지원합니다.  
  
|예외 매크로|설명|  
|---------------------|-----------------|  
|FE_DIVBYZERO|초기 부동 소수점 작업에서 특이성 또는 극 오류가 발생했습니다. 무한대 값이 생성되었습니다.|  
|FE_INEXACT|함수가 초기 부동 소수점 작업의 저장된 결과를 강제로 반올림했습니다.|  
|FE_INVALID|초기 부동 소수점 작업에서 도메인 오류가 발생했습니다.|  
|FE_OVERFLOW|범위 오류가 발생했습니다. 초기 부동 소수점 작업 결과가 표시하기에 너무 큽니다.|  
|FE_UNDERFLOW|초기 부동 소수점 작업 결과가 완전히 정확하게 표시하기에 너무 작습니다. 비정상적인 값이 생성되었습니다.|  
|FE_ALLEXCEPT|모든 지원되는 부동 소수점 예외의 비트 OR입니다.|  
  
 `excepts` 인수는 0, 예외 매크로 값 중 하나 또는 지원되는 예외 매크로 중 두 개 이상의 비트 OR일 수 있습니다. 지정된 예외 매크로 중 하나가 FE_OVERFLOW 또는 FE_UNDERFLOW이면 파생 작업으로 FE_INEXACT 예외가 발생할 수 있습니다.  
  
 이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
 **Microsoft 전용:** `excepts`에 지정된 예외는 FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT 순서로 발생합니다. 그러나 FE_OVERFLOW 또는 FE_UNDERFLOW가 발생하면 `excepts`에 지정되지 않은 경우에도 FE_INEXACT가 발생할 수 있습니다. **Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`feraiseexcept`|\<fenv.h>|\<cfenv>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)