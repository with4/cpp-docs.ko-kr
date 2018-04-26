---
title: free | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- free
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecb214f5b7f53682fe1f1327089836a172319015
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="free"></a>free

메모리 블록을 할당 해제하거나 해제합니다.

## <a name="syntax"></a>구문

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock* 이전에 해제 될 메모리 블록을 할당 합니다.

## <a name="remarks"></a>설명

**무료** 함수는 메모리 블록 할당 취소 (*memblock*)를 호출 하 여 이전에 할당 된 **calloc**, **malloc**, 또는 **realloc**합니다. 해제 된 바이트 수는 블록이 할당 된 경우 요청 된 바이트 수에 해당 하는 (또는의 경우에 다시 할당 된 **realloc**). 경우 *memblock* 은 **NULL**, 포인터는 무시 됩니다. 및 **무료** 즉시 반환 합니다. 잘못 된 포인터를 해제 하려고 시도 (으로 할당 되지 않은 메모리 블록에 대 한 포인터 **calloc**, **malloc**, 또는 **realloc**) 후속 할당 요청에 영향을 줄 수 및 오류가 발생 합니다.

메모리를 해제에서 오류가 발생 하는 경우 **errno** 오류의 성격에 운영 체제에서 정보를 사용 하 여 설정 합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

메모리 블록이 해제된 후 [_heapmin](heapmin.md)은 사용되지 않은 영역을 결합하고 다시 운영 체제로 릴리스하여 힙에 있는 사용 가능한 메모리 양을 최소화합니다. 운영 체제로 릴리스되지 않은 해제된 메모리는 사용 가능한 풀로 복원되고 다시 할당할 수 있습니다.

응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 **무료** 확인 [_free_dbg](free-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**무료** 표시 되어 `__declspec(noalias)`, 함수 전역 변수를 수정할 수 없도록 보장을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.

[_malloca](malloca.md)를 사용하여 할당된 메모리를 해제하려면 [_freea](freea.md)를 사용합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**free**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[malloc](malloc.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
