---
title: "데이터 정렬 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- data.alignment
dev_langs:
- C++
helpviewer_keywords:
- data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8c1e9bceaf205f6ac324033842292fe12150df27
ms.lasthandoff: 02/24/2017

---
# <a name="data-alignment"></a>데이터 맞춤
다음 C 런타임 함수는 데이터 정렬을 지원합니다.  
  
### <a name="data-alignment-routines"></a>데이터 정렬 루틴  
  
|루틴|기능|.NET Framework의 해당 값|  
|-------------|---------|-------------------------------|  
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다(디버그에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|지정된 맞춤 경계에 메모리를 할당합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|디버깅 헤더에 대한 추가 공간이 있는 지정된 정렬 경계에서 메모리 블록을 할당하고 버퍼를 덮어씁니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|힙에 할당된 메모리 블록의 크기를 반환합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|힙에 할당된 메모리 블록의 크기를 반환합니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|지정된 맞춤 경계에 메모리를 할당합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|지정된 맞춤 경계에 메모리를 할당합니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다(디버그 버전에만 해당).|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
