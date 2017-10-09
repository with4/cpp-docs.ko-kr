---
title: "_aligned_offset_realloc_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 139046ad9114971b2085be02391b8fd2362a4749
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void * _aligned_offset_realloc_dbg(  
   void *memblock,   
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
  
 [in] `size`  
 메모리 할당의 크기입니다.  
  
 [in] `alignment`  
 맞춤 값으로 2의 정수 거듭제곱이어야 합니다.  
  
 [in] `offset`  
 맞춤을 강제하는 메모리 할당으로의 오프셋입니다.  
  
 [in] `filename`  
 `aligned_offset_realloc` 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 [in] `linenumber`  
 `aligned_offset_realloc` 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 `_aligned_offset_realloc_dbg`는 다시 할당된(그리고 이동되었을 수 있는) 메모리 블록에 대한 void 포인터를 반환합니다. 크기가 0이고 버퍼 인수가 `NULL`이 아닌 경우 또는 버퍼를 지정된 크기로 확장하는 데 사용할 수 있는 메모리가 부족한 경우 반환 값은 `NULL`입니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.  
  
## <a name="remarks"></a>설명  
 `_aligned_offset_realloc_dbg`는 [_aligned_offset_realloc](../../c-runtime-library/reference/aligned-offset-realloc.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_offset_realloc_dbg`에 대한 각 호출이 `_aligned_offset_realloc`에 대한 호출로 줄어듭니다. `_aligned_offset_realloc`와 `_aligned_offset_realloc_dbg` 둘 다 기본 힙에서 메모리 블록을 다시 할당하지만 `_aligned_offset_realloc_dbg`는 여러 디버깅 기능을 수용합니다. 이러한 기능에는 메모리 블록의 사용자 부분 한쪽에서의 버퍼(어느 쪽이든지 상관없이)로 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 `filename`/`linenumber` 정보로 할당 요청의 원점을 확인하는 기능이 있습니다.  
  
 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)와 마찬가지로 `_aligned_offset_realloc_dbg`는 구조가 구조 내 오프셋에서 정렬될 수 있도록 합니다.  
  
 `_realloc_dbg`는 요청된 `newSize`보다 약간 더 많은 공간을 지정된 메모리 블록에 다시 할당합니다. `newSize`는 원래 할당된 메모리 블록의 크기보다 더 크거나 작을 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 메모리 블록이 이동하면 원래 블록의 내용을 덮어씁니다.  
  
 이 함수는 메모리 할당에 실패한 경우 또는 요청된 크기가 `errno`보다 큰 경우 `ENOMEM`를 `_HEAP_MAXREQ`으로 설정합니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요. 또한 `_aligned_offset_realloc_dbg`는 매개 변수의 유효성을 검사합니다. `alignment`가 2의 거듭제곱이 아니거나 `offset`이 `size`와 같거나 크고 0이 아닌 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_aligned_offset_realloc_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)
