---
title: "fegetenv1 | Microsoft 문서"
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
- fetegenv
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetenv
- fenv/fegetenv
dev_langs:
- C++
helpviewer_keywords:
- fetegenv function
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 025b934ec6a2d9bc98d46cabbd13b93e263cd777
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="fegetenv"></a>fegetenv
지정된 개체에 현재 부동 소수점 환경을 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `penv`  
 현재 부동 소수점 환경 값을 포함할 `fenv_t` 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 부동 소수점 환경이 `penv`에 성공적으로 저장된 경우 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `fegetenv` 함수는 현재 부동 소수점 환경을 `penv`가 가리키는 개체에 저장합니다. 부동 소수점 환경은 부동 소수점 계산에 영향을 미치는 상태 플래그 및 제어 모드의 집합입니다. 여기에는 부동 소수점 예외에 대한 상태 플래그와 반올림 방향 모드가 포함됩니다.  `penv`가 유효한 `fenv_t` 개체를 가리키지 않으면 후속 동작이 정의 해제됩니다.  
  
 이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`fegetenv`|\<fenv.h>|\<cfenv>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)