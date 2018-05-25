---
title: _aligned_offset_malloc_dbg | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd938b935ff5e69adf4d4e56cd70693cfd1a872d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

지정된 맞춤 경계에 메모리를 할당합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
요청된 메모리 할당 크기입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 된 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

할당 된 메모리 블록에 대 한 포인터 또는 **NULL** 작업이 실패 합니다.

## <a name="remarks"></a>설명

**_aligned_offset_malloc_dbg** 의 디버그 버전이 [_aligned_offset_malloc](aligned-offset-malloc.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_offset_malloc_dbg** 에 대 한 호출으로 줄어듭니다 **_aligned_offset_malloc**합니다. 둘 다 **_aligned_offset_malloc** 및 **_aligned_offset_malloc_dbg** 기본 힙에서 메모리 블록을 할당 하지만 **_aligned_offset_malloc_dbg** 여러 제공 디버깅 기능: 블록 형식 매개 변수로 특정 할당 형식 추적, 즉 누수를 테스트 하는 블록의 사용자 부분 양쪽에서의 버퍼 및 *filename*/*linenumber* 정보로 할당 요청의 원점을 확인 하 합니다.

**_aligned_offset_malloc_dbg** 는 요청 된 것 보다 약간 더 많은 공간을 가진 메모리 블록 할당 *크기*합니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 블록이 할당되면 블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.

**_aligned_offset_malloc_dbg** 맞춤; 중첩된 된 요소에 필요한 경우에 유용 예를 들어 중첩된 된 클래스에 맞춤 필요 했습니다.

**_aligned_offset_malloc_dbg** 기반 **malloc**; 자세한 내용은 참조 [malloc](malloc.md)합니다.

이 함수는 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 한 경우 또는 요청 된 크기 보다 큰 경우 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**, 참조 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_offset_malloc** 해당 매개 변수의 유효성을 검사 합니다. 경우 *맞춤* 2의 거듭제곱이 아닌 경우 또는 *오프셋* 보다 크거나 같음 *크기* 0이 아닌 경우이 함수는 잘못 된 매개 변수 처리기를 호출 에설명된대로[ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 허용 된 경우이 함수는 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
