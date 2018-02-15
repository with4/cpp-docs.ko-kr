---
title: "feclearexcept1 | Microsoft 문서"
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
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 661e93b181005acbd822fbb3ea2a2f970bbedf3d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="feclearexcept"></a>feclearexcept
인수를 통해 지정한 부동 소수점 예외 플래그를 지우려고 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `excepts`  
 지울 예외 상태 플래그입니다.  
  
## <a name="return-value"></a>반환 값  
 `excepts`가 0이거나 모든 지정된 예외가 성공적으로 지워진 경우 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `feclearexcept` 함수는 `excepts`를 통해 지정한 부동 소수점 예외 플래그를 지우려고 합니다. 이 함수는 fenv.h에 정의된 다음 예외 매크로를 지원합니다.  
  
|예외 매크로|설명|  
|---------------------|-----------------|  
|FE_DIVBYZERO|초기 부동 소수점 작업에서 특이성 또는 극 오류가 발생했습니다. 무한대 값이 생성되었습니다.|  
|FE_INEXACT|함수가 초기 부동 소수점 작업의 저장된 결과를 강제로 반올림했습니다.|  
|FE_INVALID|초기 부동 소수점 작업에서 도메인 오류가 발생했습니다.|  
|FE_OVERFLOW|범위 오류가 발생했습니다. 초기 부동 소수점 작업 결과가 표시하기에 너무 큽니다.|  
|FE_UNDERFLOW|초기 부동 소수점 작업 결과가 완전히 정확하게 표시하기에 너무 작습니다. 비정상적인 값이 생성되었습니다.|  
|FE_ALLEXCEPT|모든 지원되는 부동 소수점 예외의 비트 OR입니다.|  
  
 `excepts` 인수는 0이거나 지원되는 예외 매크로 중 하나 이상의 비트 OR일 수 있습니다. 기타 인수 값의 결과는 정의 해제됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`feclearexcept`|\<fenv.h>|\<cfenv>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)