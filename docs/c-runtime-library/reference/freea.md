---
title: _freea | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _freea
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
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac01f965e159dae19bbbd748c1692058063a211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="freea"></a>_freea

메모리 블록을 할당 해제하거나 해제합니다.

## <a name="syntax"></a>구문

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
해제할 이전에 할당된 메모리 블록입니다.

## <a name="return-value"></a>반환 값

없음

## <a name="remarks"></a>설명

**_freea** 함수는 메모리 블록 할당 취소 (*memblock*)를 호출 하 여 이전에 할당 된 [_malloca](malloca.md)합니다. **_freea** 힙이나 스택에서에 메모리가 할당 된 경우를 확인 합니다. 스택, 할당 된 경우 **_freea** 는 아무 작업도 수행 합니다. 힙에서 할당된 경우 해제된 바이트 수는 블록이 할당될 때 요청된 바이트 수와 일치합니다. 경우 *memblock* 은 **NULL**, 포인터는 무시 됩니다. 및 **_freea** 즉시 반환 합니다. 잘못 된 포인터를 해제 하려고 시도 (으로 할당 되지 않은 메모리 블록에 대 한 포인터 **_malloca**) 후속 할당 요청에는 적용 하 고 오류가 발생할 수 있습니다.

**_freea** 호출 **무료** 메모리가 힙에 할당은 발견 되 면 내부적으로 합니다. 메모리가 힙 또는 스택에 있는지 여부는 할당된 메모리 바로 앞 주소의 메모리에 배치된 표식에 의해 결정됩니다.

메모리를 해제에서 오류가 발생 하는 경우 **errno** 오류의 성격에 운영 체제에서 정보를 사용 하 여 설정 합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

메모리 블록이 해제된 후 [_heapmin](heapmin.md)은 사용되지 않은 영역을 결합하고 다시 운영 체제로 릴리스하여 힙에 있는 사용 가능한 메모리 양을 최소화합니다. 운영 체제로 릴리스되지 않은 해제된 메모리는 사용 가능한 풀로 복원되고 다시 할당할 수 있습니다.

에 대 한 호출 **_freea** 모든 호출을 함께 사용 해야 합니다 **_malloca**합니다. 호출 하면 오류가 발생 이기도 **_freea** 동일한 메모리에 두 번입니다. 특히 응용 프로그램 C 런타임 라이브러리의 디버그 버전과 연결 때 [_malloc_dbg](malloc-dbg.md) 정의 하 여 사용 하는 기능 **_CRTDBG_MAP_ALLOC**를 더 쉽게 찾을 수 또는 에 대 한 호출을 중복 **_freea**합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**_freea** 표시 되어 `__declspec(noalias)`, 함수 전역 변수를 수정할 수 없도록 보장을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_freea**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_malloca](malloca.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
