---
title: _aligned_recalloc_dbg | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6f88e9b93de43733c23dc853f1c19352264c949
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="alignedrecallocdbg"></a>_aligned_recalloc_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_recalloc_dbg(
   void * memblock,
   size_t num,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
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

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 된 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

**_aligned_recalloc_dbg** 다시 할당 된 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 void 포인터를 반환 합니다. 반환 값은 **NULL** 경우 크기는 0이 고 버퍼 인수가 **NULL**, 없는 경우 지정 된 크기로 확장 하는 사용 가능한 메모리가 부족 하거나 합니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

메모리를 다시 할당하고 블록의 맞춤을 변경하면 오류가 발생합니다.

## <a name="remarks"></a>설명

**_aligned_recalloc_dbg** 의 디버그 버전이 [_aligned_recalloc](aligned-recalloc.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_recalloc_dbg** 에 대 한 호출으로 줄어듭니다 **_aligned_recalloc**합니다. 둘 다 **_aligned_recalloc** 및 **_aligned_recalloc_dbg** 기본 힙에서 메모리 블록 다시 할당 하지만 **_aligned_recalloc_dbg** 몇 가지 디버깅을 수용 합니다. 기능: 블록 형식 매개 변수로 특정 할당 형식 추적, 즉 누수를 테스트 하는 블록의 사용자 부분 양쪽에서의 버퍼 및 *filename*/*linenumber* 정보로 할당 요청의 원점을 확인 하 합니다.

**_aligned_recalloc_dbg** 요청된 된 크기 보다 약간 더 많은 공간을 가진 지정 된 메모리 블록 다시 할당 (*번호* * *크기*) 크거나 작은 일 수 있는 보다 원래 할당 된 메모리 블록의 크기입니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 블록의 사용자 부분은 값 0xCD로 채워지고 덮어쓰기 버퍼는 0xFD로 채워집니다.

**_aligned_recalloc_dbg** 설정 **errno** 를 **ENOMEM** 메모리 할당에 실패 하면 **EINVAL** (앞에서 언급 한 오버 헤드 포함) 필요한 메모리 양을 초과 하는 경우 반환 되 **_HEAP_MAXREQ**합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

또한 **_aligned_recalloc_dbg** 해당 매개 변수의 유효성을 검사 합니다. 경우 *맞춤* 거듭제곱이 아닌 2의이 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우이 함수는 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_recalloc_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
