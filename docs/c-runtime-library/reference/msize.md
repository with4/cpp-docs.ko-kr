---
title: _msize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _msize
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
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9e27751072891bcabc0b068cb5ca57b571d35d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402155"
---
# <a name="msize"></a>_msize

힙에 할당된 메모리 블록의 크기를 반환합니다.

## <a name="syntax"></a>구문

```C
size_t _msize(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
메모리 블록에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**_msize** 의 크기 (바이트)를 부호 없는 정수로 반환 합니다.

## <a name="remarks"></a>설명

**_msize** 함수를 호출 하 여 할당 된 메모리 블록의 바이트 단위로 크기 반환 **calloc**, **malloc**, 또는 **realloc**합니다.

응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 **_msize** 확인 [_msize_dbg](msize-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *memblock* null 포인터가 **_msize** 의 설명 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수를 설정 하는 오류 처리 되는 경우 **errno** 를 **EINVAL** 하 고-1을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

[realloc](realloc.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[_expand](expand.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
