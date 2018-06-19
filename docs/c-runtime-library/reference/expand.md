---
title: _expand | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f709df131ded856881dc171c2e1549d3d5d378e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402353"
---
# <a name="expand"></a>_expand

메모리 블록의 크기를 변경합니다.

## <a name="syntax"></a>구문

```C
void *_expand(
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

**_expand** 다시 할당 된 메모리 블록에 대 한 void 포인터를 반환 합니다. **_expand**달리 **realloc**, 블록의 크기를 변경할 이동할 수 없습니다. 따라서 충분 한 메모리 블록을 이동 하지 않고 확장할 수 있는 경우는 *memblock* 매개 변수를 **_expand** 반환 값과 같습니다.

**_expand** 반환 **NULL** 동작 중 오류가 발견 되는 경우. 예를 들어 경우 **_expand** 는 메모리 블록을 축소 하는 데 사용, 수 작은 블록 힙 또는 잘못 된 블록이 포인터에 손상을 검색 하 고 반환 **NULL**합니다.

이동 하지 않고 지정 된 크기로 확장 하는 사용 가능한 메모리가 부족, 함수 반환 **NULL**합니다. **_expand** 확장 된 크기 보다 작은 요청 된 블록을 반환 하지 않습니다. 실패 한 경우 **errno** 오류의 성격을 나타냅니다. 에 대 한 자세한 내용은 **errno**, 참조 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.

반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. 항목의 새 크기를 확인 하려면 사용 **_msize**합니다. 이외의 다른 형식에 대 한 포인터를 가져올 **void**, 반환 값에 형식 캐스팅을 사용 합니다.

## <a name="remarks"></a>설명

**_expand** 함수를 확장 하거나 힙에서 위치를 이동 하지 않고 블록을 축소 하려고 시도 하 여 이전에 할당 된 메모리 블록의 크기를 변경 합니다. *memblock* 매개 변수는 블록의 시작 부분을 가리킵니다. *크기* 매개 변수는 블록의 새 크기를 바이트 단위로 제공 합니다. 블록의 콘텐츠는 새 크기와 이전 크기 중 더 짧은 크기까지 변경 사항이 없습니다. *memblock* 해제 된 블록 수 없습니다.

> [!NOTE]
> 64 비트 플랫폼에서 **_expand** 블록 16k 크기에서이 고 따라서 낮은 조각화 힙을에 할당 된 경우 새 size가 특히에서; 현재 크기 보다 작으면 블록을 축소 수 **_expand**  변경 되지 않은 블록을 유지 하 고 반환 *memblock*합니다.

응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 **_expand** 확인 [_expand_dbg](expand-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *memblock* 가 null 포인터 이면이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수가 반환 하 고 **NULL**합니다. 경우 *크기* 보다 크면 **_HEAP_MAXREQ**, **errno** 로 설정 된 **ENOMEM** 함수 반환 **NULL**.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
