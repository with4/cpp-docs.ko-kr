---
title: _aligned_offset_realloc | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 892fa0a3de0294437f74c6dc20c0910aa5e3fe60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393578"
---
# <a name="alignedoffsetrealloc"></a>_aligned_offset_realloc

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다.

## <a name="syntax"></a>구문

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
현재 메모리 블록 포인터입니다.

*size*<br/>
메모리 할당의 크기입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

## <a name="return-value"></a>반환 값

**_aligned_offset_realloc** 다시 할당 된 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 void 포인터를 반환 합니다. 반환 값은 **NULL** 경우 크기는 0이 고 버퍼 인수가 **NULL**, 없는 경우 지정 된 크기로 확장 하는 사용 가능한 메모리가 부족 하거나 합니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

**_aligned_offset_realloc** 표시 되어 `__declspec(noalias)` 및 `__declspec(restrict)`, 함수가 전역 변수를 수정할 수 없도록 보장 하 고 포인터에 별칭이 지정 되지 않음을 반환 되었음을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="remarks"></a>설명

마찬가지로 [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_realloc** 는 구조가 구조 내 오프셋에서 정렬 될 수 있도록 합니다.

**_aligned_offset_realloc** 기반 **malloc**합니다. 사용에 대 한 자세한 내용은 **_aligned_offset_malloc**, 참조 [malloc](malloc.md)합니다. 경우 *memblock* 은 **NULL**, 함수 호출 **_aligned_offset_malloc** 내부적으로 합니다.

이 함수는 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 한 경우 또는 요청 된 크기 보다 큰 경우 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**, 참조 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_offset_realloc** 해당 매개 변수의 유효성을 검사 합니다. 경우 *맞춤* 2의 거듭제곱이 아닌 경우 또는 *오프셋* 보다 크거나 같음 *크기* 0이 아닌 경우이 함수는 잘못 된 매개 변수 처리기를 호출 에설명된대로[ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우이 함수는 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>예제

자세한 내용은 [_aligned_malloc](aligned-malloc.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 맞춤](../../c-runtime-library/data-alignment.md)<br/>
