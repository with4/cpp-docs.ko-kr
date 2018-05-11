---
title: _recalloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _recalloc
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
- _recalloc
- recalloc
dev_langs:
- C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c4ae06fbd3d10f1014fe1c879b482f30302a4f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="recalloc"></a>_recalloc

조합을 **realloc** 및 **calloc**합니다. 메모리에 배열을 다시 할당하고 해당 요소를 0으로 초기화합니다.

## <a name="syntax"></a>구문

```C
void *_recalloc(
   void *memblock
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
이전에 할당된 메모리 블록에 대한 포인터입니다.

*번호*<br/>
요소의 수입니다.

*size*<br/>
각 요소의 길이입니다(바이트).

## <a name="return-value"></a>반환 값

**_recalloc** 반환는 **void** 다시 할당 된 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 포인터입니다.

지정 된 크기로 확장 하는 사용 가능한 메모리가 부족 없는 경우 원래 블록은 변경 되지 않습니다, 그리고 및 **NULL** 반환 됩니다.

요청 된 크기가 0 인 경우가 가리키는 블록 *memblock* 해제 됩니다; 반환 값은 **NULL**, 및 *memblock* 해제 된 블록의 가리키는 그대로 유지 됩니다.

반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. 이외의 다른 형식에 대 한 포인터를 가져올 **void**, 반환 값에 형식 캐스팅을 사용 합니다.

## <a name="remarks"></a>설명

**_recalloc** 함수는 할당 된 메모리 블록의 크기를 변경 합니다. *memblock* 인수 메모리 블록의 시작 부분을 가리킵니다. 경우 *memblock* 은 **NULL**, **_recalloc** 동일한 방식으로 동작 [calloc](calloc.md) 새 블록을 할당 하 고 *번호*  *  *크기* 바이트입니다. 각 요소는 0으로 초기화됩니다. 경우 *memblock* 않습니다 **NULL**, 것에 대 한 이전 호출에서 반환 된 포인터 **calloc**, [malloc](malloc.md), 또는 [realloc ](realloc.md).

새 블록 일 수 있으므로 새 메모리 위치에 의해 반환 된 포인터 **_recalloc** 가 같지 않을 통해 전달 된 포인터는 *memblock* 인수입니다.

**_recalloc** 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 하거나 메모리 양을 초과 요청한 경우 **_HEAP_MAXREQ**합니다. 이 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

**recalloc** 호출 **realloc** 는 c + +를 사용 하려면 [_set_new_mode](set-new-mode.md) 새 처리기 모드를 설정 하는 함수입니다. 새 처리기 모드 나타냅니다 실패 여부 **realloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 [_set_new_handler](set-new-handler.md)합니다. 기본적으로 **realloc** 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의할 수 있도록, **_recalloc** 가 메모리 할당에 실패 **realloc** 같은 새 처리기 루틴을 호출 방식으로 **새** 연산자 동일한 이유로 실패할 때 수행 하지 않습니다. 기본값을 재정의하려면 다음을

```C
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다.

응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 **_recalloc** 확인 [_recalloc_dbg](recalloc-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**_recalloc** 표시 되어 `__declspec(noalias)` 및 `__declspec(restrict)`, 함수가 전역 변수를 수정할 수 없도록 보장 되 고 반환 된 포인터 별칭이 지정 되지 않음을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[free](free.md)<br/>
[링크 옵션](../../c-runtime-library/link-options.md)<br/>
