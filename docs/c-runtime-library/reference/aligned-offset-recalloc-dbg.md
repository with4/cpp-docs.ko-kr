---
title: "_aligned_offset_recalloc_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
dev_langs: C++
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3697b62ff9926cc15d8330c94d845fe80f7c8ec5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="alignedoffsetrecallocdbg"></a>_aligned_offset_recalloc_dbg
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void * _aligned_offset_recalloc_dbg(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `memblock`  
 현재 메모리 블록 포인터입니다.  
  
 [in] `num`  
 요소의 수입니다.  
  
 [in] `size`  
 각 요소의 길이입니다(바이트).  
  
 [in] `alignment`  
 맞춤 값으로 2의 정수 거듭제곱이어야 합니다.  
  
 [in] `offset`  
 맞춤을 강제하는 메모리 할당으로의 오프셋입니다.  
  
 [in] `filename`  
 `realloc` 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 [in] `linenumber`  
 `realloc` 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 `_aligned_offset_recalloc_dbg`는 다시 할당된(그리고 이동되었을 수 있는) 메모리 블록에 대한 void 포인터를 반환합니다. 크기가 0이고 버퍼 인수가 `NULL`이 아닌 경우 또는 버퍼를 지정된 크기로 확장하는 데 사용할 수 있는 메모리가 부족한 경우 반환 값은 `NULL`입니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.  
  
## <a name="remarks"></a>설명  
 `_aligned_offset_realloc_dbg`는 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_offset_recalloc_dbg`에 대한 각 호출이 `_aligned_offset_recalloc`에 대한 호출로 줄어듭니다. `_aligned_offset_recalloc`와 `_aligned_offset_recalloc_dbg` 둘 다 기본 힙에서 메모리 블록을 다시 할당하지만 `_aligned_offset_recalloc_dbg`는 여러 디버깅 기능을 수용합니다. 이러한 기능에는 메모리 블록의 사용자 부분 한쪽에서의 버퍼(어느 쪽이든지 상관없이)로 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 `filename`/`linenumber` 정보로 할당 요청의 원점을 확인하는 기능이 있습니다.  
  
 `_aligned_offset_realloc_dbg`는 요청된 `newSize`보다 약간 더 많은 공간을 지정된 메모리 블록에 다시 할당합니다. `newSize`는 원래 할당된 메모리 블록의 크기보다 더 크거나 작을 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 메모리 블록이 이동하면 원래 블록의 내용을 덮어씁니다.  
  
 메모리 할당에 실패한 경우 또는 요청된 크기(`num` * `size`)가 `_HEAP_MAXREQ`보다 큰 경우 이 함수는 `errno`를 `ENOMEM`으로 설정합니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요. 또한 `_aligned_offset_recalloc_dbg`는 매개 변수의 유효성을 검사합니다. `alignment`가 2의 거듭제곱이 아니거나 `offset`이 요청된 크기와 같거나 크고 0이 아닌 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_aligned_offset_recalloc_dbg`|\<malloc.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)