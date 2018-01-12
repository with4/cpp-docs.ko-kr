---
title: fesetenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: fesetenv
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
- fesetenv
- fenv/fesetenv
dev_langs: C++
helpviewer_keywords: fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64e630afb575523abcb790c29dcd198ba34f263b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fesetenv"></a>fesetenv
현재 부동 소수점 환경을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `penv`  
 [fegetenv](fegetenv1.md) 또는 [feholdexcept](feholdexcept2.md)를 호출하여 설정한 부동 소수점 환경을 포함하는 `fenv_t` 개체에 대한 포인터입니다. FE_DFL_ENV 매크로를 사용하여 기본 시작 부동 소수점 환경을 지정할 수도 있습니다.  
  
## <a name="return-value"></a>반환 값  
 환경이 성공적으로 설정된 경우 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `fesetenv` 함수는 `penv`가 가리키는 `fenv_t` 개체에 저장된 값에 따라 현재 부동 소수점 환경을 설정합니다. 부동 소수점 환경은 부동 소수점 계산에 영향을 미치는 상태 플래그 및 제어 모드의 집합입니다. 여기에는 부동 소수점 예외에 대한 상태 플래그와 반올림 모드가 포함됩니다.  `penv`가 FE_DFL_ENV가 아니거나 유효한 `fenv_t` 개체를 가리키지 않을 경우 후속 동작이 정의 해제됩니다.  
  
 이 함수를 호출하면 `penv` 개체에 있는 예외 상태 플래그가 설정되지만 해당 예외가 발생하지 않습니다.  
  
 이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`fesetenv`|\<fenv.h>|\<cfenv>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)