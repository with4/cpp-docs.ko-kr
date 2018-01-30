---
title: "_free_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 575c683ed1726d9bcaf5e4a1eb850f4b589b4492
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="freedbg"></a>_free_dbg
힙의 메모리 블록을 해제합니다(디버그 버전에만 해당함).  
  
## <a name="syntax"></a>구문  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `userData`  
 해제할 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `blockType`  
 해제할 할당된 메모리 블록의 형식입니다(`_CLIENT_BLOCK`, `_NORMAL_BLOCK` 또는 `_IGNORE_BLOCK`).  
  
## <a name="remarks"></a>설명  
 `_free_dbg` 함수는 [free](../../c-runtime-library/reference/free.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_free_dbg`에 대한 각 호출이 `free`에 대한 호출로 줄어듭니다. _`free` 및 `_free_dbg`는 둘 다 기본 힙에서 메모리 블록을 해제하지만 `_free_dbg`에는 메모리 부족 조건을 시뮬레이트하기 위해 해제된 블록을 힙의 연결된 목록에 보관하는 기능과 특정 할당 형식을 해제할 수 있는 블록 형식 매개 변수라는 두 가지 디버깅 기능이 있습니다.  
  
 `_free_dbg`는 해제 작업을 수행하기 전에 지정된 파일과 블록 위치 모두에 대해 유효성 검사를 수행합니다. 응용 프로그램에서는 이러한 유효성 검사 정보를 제공하지 않습니다. 메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다. [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 `_CRTDBG_DELAY_FREE_MEM_DF` 비트 필드가 설정되면 빈 블록은 값 0xDD로 채워지고, 빈 블록에는 `_FREE_BLOCK` 블록 형식이 할당되고, 메모리 블록에 대한 힙의 연결된 목록에서 보관됩니다.  
  
 메모리 해제 중 오류가 발생하면 운영 체제에서 제공하는 실패 특성에 대한 정보를 바탕으로 `errno`가 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
 `_free_dbg`를 사용하는 방법에 대한 샘플은 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)