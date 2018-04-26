---
title: _CrtSetAllocHook | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58ca8ba1894cb72f43965bdfbbc079f40d9e0b9e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook

클라이언트 정의 할당 함수를 C 런타임 디버그 메모리 할당 프로세스에 연결함으로써 설치합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>매개 변수

*allocHook*<br/>
C 런타임 디버그 메모리 할당 프로세스에 연결할 새로운 클라이언트 정의 할당 함수입니다.

## <a name="return-value"></a>반환 값

이전에 정의 된 할당 후크 함수 반환 또는 **NULL** 경우 *allocHook* 은 **NULL**합니다.

## <a name="remarks"></a>설명

**_CrtSetAllocHook** 응용 프로그램 C 런타임 디버그 라이브러리 메모리 할당 프로세스에는 자체 할당 함수를 후크 할 수 있습니다. 결과적으로 메모리 블록을 할당, 재할당 또는 해제하기 위해 디버그 할당 함수를 호출할 때마다 응용 프로그램의 후크 함수 호출이 트리거됩니다. **_CrtSetAllocHook** 나중에 대 한 할당 정보를 기록 하 고 할당 패턴을 검사 하는 기능 응용 프로그램 메모리가 부족 하 여 상황을 어떻게 처리 하는지 테스트 하기 위한 간편한 방법으로 응용 프로그램을 제공 합니다. 분석 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 정의 되지 않은에 대 한 호출이 **_CrtSetAllocHook** 전처리 중 제거 됩니다.

**_CrtSetAllocHook** 함수에 지정 된 새 할당 클라이언트 정의 함수를 설치 *allocHook* 이전에 정의한 후크 함수를 반환 합니다. 다음 예제에서는 클라이언트 정의 할당 후크가 어떻게 프로토타입화되어야 하는지 보여 줍니다.

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

**allocType** 인수는 할당 연산의 형식을 지정 합니다. (**_HOOK_ALLOC**, **_HOOK_REALLOC**, 및 **_HOOK_FREE**)를 할당 후크 함수에 대 한 호출에 트리거됩니다. 트리거 할당 형식이 언제가 **_HOOK_FREE**, *userData* 해제 하려고 합니다. 메모리 블록의 사용자 데이터 섹션에 대 한 포인터입니다. 그러나 트리거 할당 유형을 **_HOOK_ALLOC** 또는 **_HOOK_REALLOC**, *userData* 은 **NULL** 메모리 차단 하기 때문에 할당 되지 않은 아직 있습니다.

*크기* 메모리의 크기를 바이트 단위로 차단 지정 *blockType* 메모리 블록의 형식을 나타내는 *requestNumber* 메모리 블록의 개체 할당 순서 번호는 경우 사용 가능한 *filename* 및 **lineNumber** 트리거 할당 작업이 시작 된 소스 파일 이름과 줄 번호를 지정 합니다.

후크 함수에서 프로세스가 완료되면 후크 함수는 부울 값을 반환해야 합니다. 이를 통해 기본 C 런타임 할당 프로세스에 계속 진행하는 방식을 알려 줍니다. 후크 함수를 사용 하 여 지속적으로 면 후크 함수에 호출 되지 후크 함수를 반환 해야 하는 기본 할당 프로세스를가 하는 경우 **TRUE**합니다. 이렇게 하면 원래 트리거 할당 작업이 실행됩니다. 이 구현을 사용하여, 후크 함수는 현재 할당 작업 또는 디버그 힙의 상태를 방해하지 않고 향후 분석을 위해 할당 정보를 수집하고 저장할 수 있습니다.

후크 함수도 계속 할당 작업 트리거를 호출한, 실패 한 경우 후크 함수를 반환 해야 하는 기본 할당 프로세스를가 하는 경우 **FALSE**합니다. 이 구현을 사용하여, 후크 함수는 다양한 메모리 조건 및 디버그 힙 상태를 시뮬레이트하여 응용 프로그램에서 각 상황을 처리하는 방법을 테스트할 수 있습니다.

후크 함수를 지우려면 전달 **NULL** 를 **_CrtSetAllocHook**합니다.

방법에 대 한 자세한 내용은 **_CrtSetAllocHook** 기타 메모리 관리 기능 또는 자신의 클라이언트 정의 후크 함수 작성, 참조 하는 방법을 함께 사용할 수 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)합니다.

> [!NOTE]
> **_CrtSetAllocHook** 지원 되지 않습니다 **/clr: pure**합니다. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 제거 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

샘플을 사용 하는 방법에 대 한 **_CrtSetAllocHook**, 참조 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>
