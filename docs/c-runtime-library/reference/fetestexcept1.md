---
title: fetestexcept | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
dev_langs:
- C++
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 599c60134f9c509fd14087bafba79cd9b73ccaa6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="fetestexcept"></a>fetestexcept

지정된 부동 소수점 예외 상태 플래그 중 현재 설정되어 있는 예외 상태 플래그를 확인합니다.

## <a name="syntax"></a>구문

```C
int fetestexcept(
   int excepts
);

```

### <a name="parameters"></a>매개 변수

*excepts*<br/>
테스트할 부동 소수점 상태 플래그의 비트 OR입니다.

## <a name="return-value"></a>반환 값

성공할 경우 현재 설정된 예외 상태 플래그에 해당하는 부동 소수점 예외 매크로의 비트 OR가 포함된 비트 마스크를 반환합니다. 예외가 설정되지 않은 경우 0을 반환합니다.

## <a name="remarks"></a>설명

fetestexcept 함수를 사용하여 부동 소수점 작업을 통해 어떤 예외가 발생했는지 확인합니다. 사용 하 여는 *excepts* 매개 변수를 테스트 하는 예외 상태 플래그를 지정 합니다. **fetestexcept** 함수에 정의 된 이러한 예외 매크로 사용 하 여 \<fenv.h >에서 *excepts* 와 반환 값:

|예외 매크로|설명|
|---------------------|-----------------|
|FE_DIVBYZERO|초기 부동 소수점 작업에서 특이성 또는 극 오류가 발생했습니다. 무한대 값이 생성되었습니다.|
|FE_INEXACT|함수가 초기 부동 소수점 작업의 저장된 결과를 강제로 반올림했습니다.|
|FE_INVALID|초기 부동 소수점 작업에서 도메인 오류가 발생했습니다.|
|FE_OVERFLOW|범위 오류가 발생했습니다. 초기 부동 소수점 작업 결과가 표시하기에 너무 큽니다.|
|FE_UNDERFLOW|초기 부동 소수점 작업 결과가 완전히 정확하게 표시하기에 너무 작습니다. 비정상적인 값이 생성되었습니다.|
|FE_ALLEXCEPT|모든 지원되는 부동 소수점 예외의 비트 OR입니다.|

지정 된 *excepts* 인수 지원 되는 부동 소수점 예외 매크로 또는 비트 또는 두 개 이상의 매크로 중 하나는 0이 될 수 있습니다. 다른 모든의 효과 *excepts* 인수 값이 정의 되지 않습니다.

이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
