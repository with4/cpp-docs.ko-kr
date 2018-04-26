---
title: _CrtMemDifference | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtMemDifference
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
apitype: DLLExport
f1_keywords:
- _CrtMemDifference
- CrtMemDifference
dev_langs:
- C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27fb436c438daac7415ba3c0e7581611414c9c4a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="crtmemdifference"></a>_CrtMemDifference

두 메모리 상태를 비교하고 해당 차이점을 반환합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>매개 변수

*stateDiff*<br/>
에 대 한 포인터는 **_CrtMemState** 반환 된 두 메모리 상태의 차이점을 저장 하는 데 사용 되는 구조입니다.

*oldState*<br/>
이전 메모리 상태에 대 한 포인터 (**_CrtMemState** 구조).

*newState*<br/>
이후 메모리 상태에 대 한 포인터 (**_CrtMemState** 구조).

## <a name="return-value"></a>반환 값

메모리 상태가 현저 하 게 다른, **_CrtMemDifference** TRUE를 반환 합니다. 그렇지 않은 경우 이 함수는 FALSE를 반환합니다.

## <a name="remarks"></a>설명

**_CrtMemDifference** 비교 하 여 작동 *oldState* 및 *newState* 고 차이점을 저장 하 고 *stateDiff*는 다음을 수행할 수 메모리 누수 및 기타 메모리 문제를 감지 하는 응용 프로그램에서 사용할 수 있습니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtMemDifference** 전처리 중 제거 됩니다.

*newState* 및 *oldState* 각각에 대 한 유효한 포인터 여야 합니다는 **_CrtMemState** 으로 채워진는 Crtdbg.h에 정의 된 구조 [_CrtMemCheckpoint](crtmemcheckpoint.md)호출 하기 전에 **_CrtMemDifference**합니다. *stateDiff* 의 이전에 할당 된 인스턴스에 대 한 포인터 여야 합니다는 **_CrtMemState** 구조입니다. 경우 *stateDiff*, *newState*, 또는 *oldState* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 로 설정 된 **EINVAL** 하 고 함수는 FALSE를 반환 합니다.

**_CrtMemDifference** 비교는 **_CrtMemState** 필드 값에 있는 블록의 *oldState* 의 *newState* 에결과저장하고*stateDiff*합니다. 할당된 블록 형식의 수 또는 각 형식에 대해 할당된 총 블록 수가 두 메모리 상태 간에 다를 경우 상태가 현저하게 다르다고 합니다. 할당 된 한 번에 총 할당 차이 및 두 상태에 대 한 두 가지 상태에도 저장에 대 한 최대 크기의 차이 *stateDiff*합니다.

기본적으로 내부 C 런타임 블록 (**_CRT_BLOCK**) 메모리 상태 작업에 포함 되지 않습니다. [_CrtSetDbgFlag](crtsetdbgflag.md) 를 켜려면 함수를 사용할 수 있습니다는 **_CRTDBG_CHECK_CRT_DF** 비트의 **_crtDbgFlag** 이러한 블록을 누수 감지 및 기타 메모리 상태를 포함 하도록 작업입니다. 해제 된 메모리 블록 (**_FREE_BLOCK**) 하지 않게 **_CrtMemDifference** TRUE를 반환 합니다.

힙 상태 함수에 대 한 자세한 내용은 및 **_CrtMemState** 구조, 참조 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
