---
title: _aligned_recalloc | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_recalloc
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
- aligned_recalloc
- _aligned_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae20d71dc3a6e23b29c76166e1a09fab8afaf6f9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="alignedrecalloc"></a>_aligned_recalloc

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다.

## <a name="syntax"></a>구문

```C
void * _aligned_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
현재 메모리 블록 포인터입니다.

*번호*<br/>
요소의 수입니다.

*size*<br/>
각 요소의 크기입니다(바이트).

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

## <a name="return-value"></a>반환 값

**_aligned_recalloc** 다시 할당 된 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 void 포인터를 반환 합니다. 반환 값은 **NULL** 경우 크기는 0이 고 버퍼 인수가 **NULL**, 없는 경우 지정 된 크기로 확장 하는 사용 가능한 메모리가 부족 하거나 합니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

메모리를 다시 할당하고 블록의 맞춤을 변경하면 오류가 발생합니다.

## <a name="remarks"></a>설명

**_aligned_recalloc** 기반 **malloc**합니다. 사용에 대 한 자세한 내용은 **_aligned_offset_malloc**, 참조 [malloc](malloc.md)합니다.

이 함수는 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 한 경우 또는 요청 된 크기 보다 큰 경우 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**, 참조 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_recalloc** 해당 매개 변수의 유효성을 검사 합니다. 경우 *맞춤* 거듭제곱이 아닌 2의이 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우이 함수는 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc.h>|

## <a name="see-also"></a>참고자료

[데이터 맞춤](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
