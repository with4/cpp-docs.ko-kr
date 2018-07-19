---
title: _CrtMemDumpAllObjectsSince | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24cf01facaba326c36454ea5410da8dbb05848f2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396871"
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

프로그램 실행의 시작부터 또는 지정된 힙 상태에서 힙에 있는 개체에 대한 정보를 덤프합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>매개 변수

*상태* 시작에서 덤프를 힙 상태에 대 한 포인터 또는 **NULL**합니다.

## <a name="remarks"></a>설명

**_CrtMemDumpAllObjectsSince** 함수는 사용자가 읽을 수 있는 형태로 힙에 할당 된 개체의 디버그 헤더 정보를 덤프 합니다. 덤프 정보는 응용 프로그램에서 할당을 추적하고 메모리 문제를 검색하는 데 사용할 수 있습니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtMemDumpAllObjectsSince** 전처리 중 제거 됩니다.

**_CrtMemDumpAllObjectsSince** 값이 사용 하는 *상태* 매개 변수 덤프 작업을 시작 하는 위치를 결정 합니다. 지정 된 힙 상태에서 덤프를 시작 하는 *상태* 매개 변수는에 대 한 포인터 여야 합니다는 **_CrtMemState** 으로 채워진 구조 [_CrtMemCheckpoint](crtmemcheckpoint.md) 하기 전에 **_CrtMemDumpAllObjectsSince** 호출 되었습니다. 때 *상태* 은 **NULL**를 함수 시작 프로그램 실행의 시작 부분부터 덤프 합니다.

응용 프로그램이 덤프 후크 함수를 호출 하 여 설치 하는 경우 [_CrtSetDumpClient](crtsetdumpclient.md), 때마다 **_CrtMemDumpAllObjectsSince** 정보에 대 한 덤프는 **_CLIENT_BLOCK** 유형 블록도 응용 프로그램에서 제공 하는 덤프 함수를 호출 합니다. 기본적으로 내부 C 런타임 블록 (**_CRT_BLOCK**) 메모리 덤프 작업에 포함 되지 않습니다. [_CrtSetDbgFlag](crtsetdbgflag.md) 를 켜려면 함수를 사용할 수 있습니다는 **_CRTDBG_CHECK_CRT_DF** 비트의 **_crtDbgFlag** 이러한 블록을 포함 하도록 합니다. 또한 해제되거나 무시된 것으로 표시된 블록(**_FREE_BLOCK**, **_IGNORE_BLOCK**)은 메모리 덤프에 포함되지 않습니다.

힙 상태 함수에 대 한 자세한 내용은 및 **_CrtMemState** 구조, 참조 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

샘플을 사용 하는 방법에 대 한 **_CrtMemDumpAllObjectsSince**, 참조 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
