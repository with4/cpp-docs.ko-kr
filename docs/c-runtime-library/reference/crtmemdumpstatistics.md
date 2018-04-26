---
title: _CrtMemDumpStatistics | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69a96cf29d4cb9d7f6dbec3f079852beb528778d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics

지정된 힙 상태에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>매개 변수

*상태* 덤프할 힙 상태에 대 한 포인터입니다.

## <a name="remarks"></a>설명

**_CrtMemDumpStatistics** 함수는 지정 된 사용자가 읽을 수 있는 형태로 힙 상태에 대 한 디버그 헤더 정보를 덤프 합니다. 덤프 통계는 응용 프로그램에서 할당을 추적하고 메모리 문제를 감지하는 데 사용할 수 있습니다. 메모리 상태에는 특정 힙 상태나 두 상태 간의 차이가 포함될 수 있습니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtMemDumpStatistics** 전처리 중 제거 됩니다.

*상태* 매개 변수는에 대 한 포인터 여야 합니다는 **_CrtMemState** 으로 채워진 구조 [_CrtMemCheckpoint](crtmemcheckpoint.md) 반환한 또는 [_ CrtMemDifference](crtmemdifference.md) 전에 **_CrtMemDumpStatistics** 호출 됩니다. 경우 *상태* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 및 아무 작업도 수행 합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

힙 상태 함수에 대 한 자세한 내용은 및 **_CrtMemState** 구조, 참조 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)만 해당합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
