---
title: _aligned_offset_realloc_dbg | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee9dec91e8e5173d3933b8637ec767bd160cc225
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_offset_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
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

*filename*<br/>
요청한 소스 파일의 이름에 대 한 포인터는 **aligned_offset_realloc** 작업 또는 **NULL**합니다.

*linenumber*<br/>
소스 파일의 줄 번호 위치는 **aligned_offset_realloc** 작업이 요청 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

**_aligned_offset_realloc_dbg** 다시 할당 된 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 void 포인터를 반환 합니다. 반환 값은 **NULL** 경우 크기는 0이 고 버퍼 인수가 **NULL**, 없는 경우 지정 된 크기로 확장 하는 사용 가능한 메모리가 부족 하거나 합니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

## <a name="remarks"></a>설명

**_aligned_offset_realloc_dbg** 의 디버그 버전이 [_aligned_offset_realloc](aligned-offset-realloc.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_offset_realloc_dbg** 에 대 한 호출으로 줄어듭니다 **_aligned_offset_realloc**합니다. 둘 다 **_aligned_offset_realloc** 및 **_aligned_offset_realloc_dbg** 기본 힙에서 메모리 블록 다시 할당 하지만 **_aligned_offset_realloc_dbg** 수용 여러 디버깅 특징: 블록 형식 매개 변수로 특정 할당 형식 추적, 즉 누수를 테스트 하는 블록의 사용자 부분 양쪽에서의 버퍼 및 *filename*/*linenumber*  정보로 할당 요청의 원점을 확인 하 합니다.

마찬가지로 [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_realloc_dbg** 는 구조가 구조 내 오프셋에서 정렬 될 수 있도록 합니다.

**_realloc_dbg** 는 요청 된 것 보다 약간 더 많은 공간을 가진 지정 된 메모리 블록 다시 할당 *newSize*합니다. *newSize* 원래 할당 된 메모리 블록의 크기 보다 크거나 작은지 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 메모리 블록이 이동하면 원래 블록의 내용을 덮어씁니다.

이 함수는 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 한 경우 또는 요청 된 크기 보다 큰 경우 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**, 참조 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_offset_realloc_dbg** 해당 매개 변수의 유효성을 검사 합니다. 경우 *맞춤* 2의 거듭제곱이 아닌 경우 또는 *오프셋* 보다 크거나 같음 *크기* 0이 아닌 경우이 함수는 잘못 된 매개 변수 처리기를 호출 에설명된대로[ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우이 함수는 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_realloc_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
