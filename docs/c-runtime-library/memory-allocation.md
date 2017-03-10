---
title: "메모리 할당 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: 10
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
ms.openlocfilehash: ae7869beb76e5e1f0514c3459beab65530e31cba
ms.lasthandoff: 02/24/2017

---
# <a name="memory-allocation"></a>메모리 할당
다음 루틴을 사용하여 메모리를 할당, 확보 및 다시 할당합니다.  
  
### <a name="memory-allocation-routines"></a>메모리 할당 루틴  
  
|루틴|기능|.NET Framework의 해당 값|  
|-------------|---------|-------------------------------|  
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|스택에서 메모리 할당|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[calloc](../c-runtime-library/reference/calloc.md)|할당된 블록에서 모든 바이트를 0으로 초기화하는 배열에 저장소 할당|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|`calloc`의 디버그 버전,런타임 라이브러리의 디버그 버전에서만 사용 가능|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|할당된 블록 확보|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|할당된 블록 확보|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_expand](../c-runtime-library/reference/expand.md)|이동하지 않고 메모리 블록을 확장명 또는 축소|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|`_expand`의 디버그 버전,런타임 라이브러리의 디버그 버전에서만 사용 가능|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[free](../c-runtime-library/reference/free.md)|할당된 블록 확보|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|`free`의 디버그 버전,런타임 라이브러리의 디버그 버전에서만 사용 가능|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_freea](../c-runtime-library/reference/freea.md)|스택에서 할당된 블록 확보|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|CRT 힙의 Win32 HANDLE을 가져옵니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_heapadd](../c-runtime-library/heapadd.md)|힙에 메모리 추가|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|일관성을 위한 힙 검사|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|힙에서 사용하지 않는 메모리 해제|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_heapset](../c-runtime-library/heapset.md)|지정된 값으로 빈 힙 항목 채우기|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|힙의 각 항목에 대한 정보 반환|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[malloc](../c-runtime-library/reference/malloc.md)|힙에서 메모리 블록 할당|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|`malloc`의 디버그 버전,런타임 라이브러리의 디버그 버전에서만 사용 가능|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_msize](../c-runtime-library/reference/msize.md)|할당된 블록 크기 반환|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|`_msize`의 디버그 버전,런타임 라이브러리의 디버그 버전에서만 사용 가능|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[new](../c-runtime-library/operator-new-crt.md)|힙에서 메모리 블록 할당|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|힙에서 메모리 블록 할당|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|`_set_new_handler`가 설정한 대로 현재 새 처리기 루틴 주소 반환|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|`_set_new_mode`에 대한 `malloc`로 설정된 새 처리기 모드를 나타내는 정수 반환|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[realloc](../c-runtime-library/reference/realloc.md)|새 크기로 블록 다시 할당|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|`realloc`의 디버그 버전,런타임 라이브러리의 디버그 버전에서만 사용 가능|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|`new` 연산자가 메모리 할당에 실패하고 C++ 표준 라이브러리의 컴파일을 사용하도록 설정한 경우 오류 처리 메커니즘 사용|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|`malloc`에 대해 새 처리기 모드 설정|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
