---
title: "_aligned_offset_malloc_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: fb6714506013bcaf9e4d5f6064d7bb98f8e56562
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg
지정된 맞춤 경계에 메모리를 할당합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `size`  
 요청된 메모리 할당 크기입니다.  
  
 [in] `alignment`  
 맞춤 값으로 2의 정수 거듭제곱이어야 합니다.  
  
 [in] `offset`  
 맞춤을 강제하는 메모리 할당으로의 오프셋입니다.  
  
 [in] `filename`  
 할당 작업 또는 NULL을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 [in] `linenumber`  
 할당 작업이 요청되었거나 NULL인 소스 파일의 줄 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 할당된 메모리 블록에 대한 포인터로 작업 실패 시 `NULL`입니다.  
  
## <a name="remarks"></a>설명  
 `_aligned_offset_malloc_dbg`는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_offset_malloc_dbg`에 대한 각 호출이 `_aligned_offset_malloc`에 대한 호출로 줄어듭니다. `_aligned_offset_malloc`와 `_aligned_offset_malloc_dbg` 둘 다 기본 힙에서 메모리 블록을 할당하지만 `_aligned_offset_malloc_dbg`는 여러 디버깅 기능을 제공합니다. 이러한 기능에는 블록의 사용자 부분 한 쪽에서의 버퍼(어느 쪽이든지 상관없이)로 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 `filename`/`linenumber` 정보로 할당 요청의 원점을 확인하는 기능이 있습니다.  
  
 `_aligned_offset_malloc_dbg`는 요청된 `size`보다 약간 큰 공간의 메모리 블록을 할당합니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 블록이 할당되면 블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.  
  
 `_aligned_offset_malloc_dbg`는 중첩된 요소에 맞춤이 필요한 상황에서 유용합니다(예: 중첩된 클래스에 맞춤이 필요한 경우).  
  
 `_aligned_offset_malloc_dbg`는 `malloc`를 기반으로 합니다. 자세한 내용은 [malloc](../../c-runtime-library/reference/malloc.md)를 참조하세요.  
  
 이 함수는 메모리 할당에 실패한 경우 또는 요청된 크기가 `errno`보다 큰 경우 `ENOMEM`를 `_HEAP_MAXREQ`으로 설정합니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요. 또한 `_aligned_offset_malloc`는 매개 변수의 유효성을 검사합니다. `alignment`가 2의 거듭제곱이 아니거나 `offset`이 `size`와 같거나 크고 0이 아닌 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)
