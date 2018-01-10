---
title: "free | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: free
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
f1_keywords: free
dev_langs: C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be3f7141a8483aa7b0d43195b08506691e34fe3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="free"></a>free
메모리 블록을 할당 해제하거나 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 해제할 이전에 할당된 메모리 블록입니다.  
  
## <a name="remarks"></a>설명  
 `free` 함수는 `calloc`, `malloc` 또는 `realloc`를 호출하여 이전에 할당된 메모리 블록(`memblock`)을 할당 해제합니다. 해제된 바이트 수는 블록이 할당(또는 `realloc`의 경우 다시 할당)될 때 요청된 바이트 수와 일치합니다. `memblock`이 `NULL`이면 포인터가 무시되고 `free`가 즉시 반환됩니다. 잘못된 포인터(`calloc`, `malloc` 또는 `realloc`를 통해 할당되지 않은 메모리 블록 포인터)를 해제하려고 하면 후속 할당 요청에 영향을 미치고 오류가 발생할 수 있습니다.  
  
 메모리 해제 중 오류가 발생하면 운영 체제에서 제공하는 실패 특성에 대한 정보를 바탕으로 `errno`가 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 메모리 블록이 해제된 후 [_heapmin](../../c-runtime-library/reference/heapmin.md)은 사용되지 않은 영역을 결합하고 다시 운영 체제로 릴리스하여 힙에 있는 사용 가능한 메모리 양을 최소화합니다. 운영 체제로 릴리스되지 않은 해제된 메모리는 사용 가능한 풀로 복원되고 다시 할당할 수 있습니다.  
  
 응용 프로그램이 디버그 버전의 C 런타임 라이브러리에 연결되면 `free`는 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)가 됩니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 `free`가 `__declspec(noalias)`로 표시되면 함수는 전역 변수를 수정하지 않도록 보장되지 않습니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.  
  
 [_malloca](../../c-runtime-library/reference/malloca.md)를 사용하여 할당된 메모리를 해제하려면 [_freea](../../c-runtime-library/reference/freea.md)를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`free`|\<stdlib.h> 및 \<malloc.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 [malloc](../../c-runtime-library/reference/malloc.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)