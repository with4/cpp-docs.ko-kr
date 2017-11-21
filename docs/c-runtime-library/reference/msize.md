---
title: _msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _msize
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
dev_langs: C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e678d5ba1abcf552fa5e4576578a5a220fe50f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="msize"></a>_msize
힙에 할당된 메모리 블록의 크기를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 메모리 블록에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `_msize`는 크기(바이트)를 부호 없는 정수로 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_msize` 함수는 `calloc`, `malloc` 또는 `realloc`을 호출하여 할당된 메모리 블록의 크기(바이트)를 반환합니다.  
  
 응용 프로그램이 디버그 버전의 C 런타임 라이브러리에 연결되면 `_msize`는 [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md)가 됩니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `memblock`이 null 포인터인 경우 `_msize`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 오류가 처리되면 함수는 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
 [realloc](../../c-runtime-library/reference/realloc.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)