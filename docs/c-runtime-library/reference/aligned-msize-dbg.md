---
title: "_aligned_msize_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
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
ms.openlocfilehash: 5a924af887defa6473c4fa8c8beeccb1d27b1411
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg
힙에 할당된 메모리 블록의 크기를 반환합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
size_t _aligned_msize_dbg(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `memblock`  
 메모리 블록에 대한 포인터입니다.  
  
 [in] `alignment`  
 맞춤 값으로 2의 정수 거듭제곱이어야 합니다.  
  
 [in] `offset`  
 맞춤을 강제하는 메모리 할당으로의 오프셋입니다.  
  
## <a name="return-value"></a>반환 값  
 크기(바이트)를 부호 없는 정수로 반환합니다.  
  
## <a name="remarks"></a>설명  
 `alignment` 및 `offset` 값은 블록을 할당한 함수에 전달된 값과 동일해야 합니다.  
  
 `_aligned_msize_dbg`는 [_aligned_msize](../../c-runtime-library/reference/aligned-msize.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_aligned_msize_dbg`에 대한 각 호출이 `_aligned_msize`에 대한 호출로 줄어듭니다. `_aligned_msize`와 `_aligned_msize_dbg`는 모두 기본 힙의 메모리 블록 크기를 계산하지만 `_aligned_msize_dbg`는 디버깅 기능을 추가하며, 반환된 크기의 메모리 블록에서 사용자 부분의 어느 한쪽에 버퍼를 포함합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `memblock`이 null 포인터이거나 `alignment`가 2의 거듭제곱이 아닌 경우 `_msize`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명한 대로 잘못된 매개 변수 처리기를 호출합니다. 오류가 처리되면 함수는 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)
