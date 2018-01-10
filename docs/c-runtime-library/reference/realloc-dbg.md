---
title: _realloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs: C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3885bfb44745d815e50012d0447060b6ff2aa985
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="reallocdbg"></a>_realloc_dbg
블록을 이동하거나 크기를 조정하여 힙에서 지정된 메모리 블록을 재할당합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void *_realloc_dbg(  
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `userData`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `newSize`  
 재할당된 블록에 대해 요청된 크기(바이트)입니다.  
  
 `blockType`  
 재할당된 블록에 대해 요청된 형식(`_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`)입니다.  
  
 `filename`  
 `realloc` 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 `realloc` 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.  
  
 `filename` 및 `linenumber` 매개 변수는 `_realloc_dbg`가 명시적으로 호출되었거나 [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의된 경우에만 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료되면 이 함수는 다시 할당된 메모리 블록의 사용자 부분에 대한 포인터를 반환하거나 새 처리기 함수를 호출하거나 NULL을 반환합니다. 반환 동작에 대한 자세한 설명은 다음 설명 섹션을 참조하세요. 새 처리기 함수를 사용하는 방법에 대한 자세한 내용은 [realloc](../../c-runtime-library/reference/realloc.md) 함수를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_realloc_dbg`는 [realloc](../../c-runtime-library/reference/realloc.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_realloc_dbg`에 대한 각 호출이 `realloc`에 대한 호출로 줄어듭니다. `realloc`와 `_realloc_dbg` 둘 다 기본 힙에서 메모리 블록을 다시 할당하지만 `_realloc_dbg`는 여러 디버깅 기능을 수용합니다. 이러한 기능에는 메모리 블록의 사용자 부분 한쪽에서의 버퍼(어느 쪽이든지 상관없이)로 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 `filename`/`linenumber` 정보로 할당 요청의 원점을 확인하는 기능이 있습니다.  
  
 `_realloc_dbg`는 요청된 `newSize`보다 약간 더 많은 공간을 지정된 메모리 블록에 다시 할당합니다. `newSize`는 원래 할당된 메모리 블록의 크기보다 더 크거나 작을 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 메모리 블록이 이동하면 원래 블록의 내용을 덮어씁니다.  
  
 메모리 할당에 실패한 경우 또는 필요한 메모리 양(앞에서 언급한 오버헤드 포함)이 `_realloc_dbg`를 초과한 경우 `errno`는 `ENOMEM`를 `_HEAP_MAXREQ`으로 설정합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_realloc_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예  
 [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md) 항목의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)