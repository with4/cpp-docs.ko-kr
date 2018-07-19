---
title: _CrtMemCheckpoint | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca83a9b9b48302e9ff4974d083d0a95796a1ef3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395515"
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

디버그 힙의 현재 상태를 가져오고 응용 프로그램에서 제공한 저장 **_CrtMemState** 구조 (디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>매개 변수

*상태* 에 대 한 포인터 **_CrtMemState** 구조 메모리 검사점으로 채울 수 있습니다.

## <a name="remarks"></a>설명

**_CrtMemCheckpoint** 함수는 지정된 된 시점에 디버그 힙의 현재 상태 스냅숏을 만듭니다. 이 스냅숏은 메모리 누수를 비롯한 여러 문제를 손쉽게 감지하도록 [_CrtMemDifference](crtmemdifference.md) 같은 기타 힙 상태 함수에 사용할 수 있습니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtMemState** 전처리 중 제거 됩니다.

응용 프로그램의 이전에 할당 된 인스턴스에 포인터를 전달 해야는 **_CrtMemState** Crtdbg.h에 정의 된 구조는 *상태* 매개 변수입니다. 경우 **_CrtMemCheckpoint** 에서 검사점을 만드는 동안 오류가 발생 하 여 함수를 생성 한 **_CRT_WARN** 문제를 설명 하는 보고서를 디버그 합니다.

힙 상태 함수에 대 한 자세한 내용은 및 **_CrtMemState** 구조, 참조 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

경우 *상태* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 로 설정 된 **EINVAL** 함수를 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 UCRT만 해당합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
