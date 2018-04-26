---
title: _aligned_free_dbg | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efbe33940a4dad3ddb3ce73809ae2dc31f6d05c6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다(디버그에만 해당).

## <a name="syntax"></a>구문

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock* 반환 된 메모리 블록에 대 한 포인터는 [_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md) 함수입니다.

## <a name="remarks"></a>설명

**_aligned_free_dbg** 함수는 디버그 버전의는 [_aligned_free](aligned-free.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_free_dbg** 에 대 한 호출으로 줄어듭니다 **_aligned_free**합니다. 둘 다 **_aligned_free** 및 **_aligned_free_dbg** 기본 힙에서 메모리 블록 하지만 **_aligned_free_dbg** 디버깅 기능을 수용: 해제 된 상태로 유지 하는 기능 메모리 부족 조건을 시뮬레이션 하는 힙의 연결된 리스트에서 차단 됩니다.

**_aligned_free_dbg** 해제 작업을 수행 하기 전에 지정 된 모든 파일과 블록 위치에 대해 유효성 검사를 수행 합니다. 응용 프로그램에서는 이러한 유효성 검사 정보를 제공하지 않습니다. 메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다. 경우는 **_CRTDBG_DELAY_FREE_MEM_DF** 비트 필드는 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그를 설정, 해제 된 블록이 할당 되는 값 0xDD, 채워집니다는 **_FREE_BLOCK** 블록 형식, 및 메모리 블록의 힙 연결된 리스트에 보관합니다.

메모리를 해제에서 오류가 발생 하는 경우 **errno** 오류의 성격에 운영 체제에서 정보를 사용 하 여 설정 합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
