---
title: feholdexcept | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs:
- C++
helpviewer_keywords:
- feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6250de98b2eb3f8cc8c475d341c1d63a79262362
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="feholdexcept"></a>feholdexcept

현재 부동 소수점 환경을 지정된 개체에 저장하고, 부동 소수점 상태 플래그를 지우고, 가능한 경우 부동 소수점 환경을 무중단 모드로 전환합니다.

## <a name="syntax"></a>구문

```C
int feholdexcept(
   fenv_t *penv
);
```

### <a name="parameters"></a>매개 변수

*penv*<br/>
에 대 한 포인터는 **fenv_t** 부동 소수점 환경 복사본을 포함 하는 개체입니다.

## <a name="return-value"></a>반환 값

경우에 함수를 성공적으로 중단 없이 부동 소수점 예외 처리를 설정할 수는 0을 반환 합니다.

## <a name="remarks"></a>설명

**feholdexcept** 함수는 현재 부동 지점 환경에서의 상태를 저장 하는 데 사용 됩니다는 **fenv_t** 가리키는 개체 *penv*, 환경 설정 하려면 부동 소수점 예외에서 실행을 중단 합니다. 이를 무중단 모드라고 합니다.  이 모드는 [fesetenv](fesetenv1.md) 또는 [feupdateenv](feupdateenv.md)를 통해 환경이 복원될 때까지 계속됩니다.

호출자로부터 하나 이상의 부동 소수점 예외를 숨겨야 하는 하위 루틴의 시작 부분에서 이 함수를 사용할 수 있습니다. 예외를 보고 하려면 단순히 지워도 원치 않는 예외를 사용 하 여 [feclearexcept,](feclearexcept1.md) 다음을 호출 하 여 중단 없이 모드를 종료 하 고 **feupdateenv**합니다.

이 함수를 사용하려면 호출 전에 `#pragma fenv_access(on)` 지시문을 사용하여 액세스를 방지할 수 있는 부동 소수점 최적화를 꺼야 합니다. 자세한 내용은 [fenv_access](../../preprocessor/fenv-access.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**feholdexcept**|\<fenv.h>|\<cfenv>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[fesetenv](fesetenv1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
