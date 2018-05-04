---
title: realloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs:
- C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6452d14e0a8630c68d5e179fd94d531db1b667ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="realloc"></a>realloc

메모리 블록을 다시 할당합니다.

## <a name="syntax"></a>구문

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
이전에 할당된 메모리 블록에 대한 포인터입니다.

*size*<br/>
새 크기(바이트)입니다.

## <a name="return-value"></a>반환 값

**realloc** 반환는 **void** 다시 할당 된 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 포인터입니다.

지정 된 크기로 확장 하는 사용 가능한 메모리가 부족 없는 경우 원래 블록은 변경 되지 않습니다, 그리고 및 **NULL** 반환 됩니다.

경우 *크기* 0가 가리키는 블록 *memblock* 해제 됩니다; 반환 값은 **NULL**, 및 *memblock* 에서 가리키고는 블록을 해제 합니다.

반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. 이외의 다른 형식에 대 한 포인터를 가져올 **void**, 반환 값에 형식 캐스팅을 사용 합니다.

## <a name="remarks"></a>설명

**realloc** 함수는 할당 된 메모리 블록의 크기를 변경 합니다. *memblock* 인수 메모리 블록의 시작 부분을 가리킵니다. 경우 *memblock* 은 **NULL**, **realloc** 동일한 방식으로 동작 **malloc** 새 블록을 할당 하 고 *크기*바이트입니다. 경우 *memblock* 않습니다 **NULL**, 것에 대 한 이전 호출에서 반환 된 포인터 **calloc**, **malloc**, 또는 **realloc** .

*크기* 인수는 블록의 새 크기 (바이트) 제공 합니다. 블록의 내용은 새 크기와 이전 크기 중 더 짧은 쪽까지는 변경되지 않습니다. 그러나 새 블록은 다른 위치에 있을 수 있습니다. 새 블록 일 수 있으므로 새 메모리 위치에 의해 반환 된 포인터 **realloc** 가 같지 않을 통해 전달 된 포인터는 *memblock* 인수입니다. **realloc** 가 0이 아니면 새로 할당 된 메모리 버퍼 증가 경우.

**realloc** 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 하거나 메모리 양을 초과 요청한 경우 **_HEAP_MAXREQ**합니다. 이 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

**realloc** 호출 **malloc** 는 c + +를 사용 하려면 [_set_new_mode](set-new-mode.md) 새 처리기 모드를 설정 하는 함수입니다. 새 처리기 모드 나타냅니다 실패 여부 **malloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 [_set_new_handler](set-new-handler.md)합니다. 기본적으로 **malloc** 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의할 수 있도록, **realloc** 가 메모리 할당에 실패 **malloc** 같은 새 처리기 루틴을 호출 방식으로 **새** 연산자는 때 이와 같은 이유로 실패 합니다. 기본값을 재정의하려면 다음을

```C
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).

응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 **realloc** 확인 [_realloc_dbg](realloc-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**realloc** 표시 되어 `__declspec(noalias)` 및 `__declspec(restrict)`, 함수가 전역 변수를 수정할 수 없도록 보장 되 고 반환 된 포인터 별칭이 지정 되지 않음을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**realloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
