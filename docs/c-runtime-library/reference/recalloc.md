---
title: _recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _recalloc
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
- _recalloc
- recalloc
dev_langs:
- C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ae78e17f66448de46e36ea7d6dc6e3121b306c68
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="recalloc"></a>_recalloc
`realloc` 및 `calloc`의 조합입니다. 메모리에 배열을 다시 할당하고 해당 요소를 0으로 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `num`  
 요소의 수입니다.  
  
 `size`  
 각 요소의 길이입니다(바이트).  
  
## <a name="return-value"></a>반환 값  
 `_recalloc`는 다시 할당된(그리고 이동되었을 수 있는) 메모리 블록에 대한 `void` 포인터를 반환합니다.  
  
 블록을 지정된 크기로 확장하는 데 사용할 수 있는 충분한 메모리가 없으면 원래 블록은 변경되지 않고 그대로 유지되며 `NULL`이 반환됩니다.  
  
 요청된 크기가 0이면 `memblock`에서 가리키는 블록이 해제됩니다. 반환 값은 `NULL`이며, `memblock`은 해제된 블록을 가리키는 상태로 유지됩니다.  
  
 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. `void`가 아닌 형식의 포인터를 가져오려면 반환 값에 형식 캐스팅을 사용합니다.  
  
## <a name="remarks"></a>설명  
 `_recalloc` 함수는 할당된 메모리 블록의 크기를 변경합니다. `memblock` 인수는 메모리 블록의 시작 부분을 가리킵니다. 경우 `memblock` 은 `NULL`, `_recalloc` 동일한 방식으로 동작 [calloc](../../c-runtime-library/reference/calloc.md) 새 블록을 할당 하 고 `num`  *  `size` 바이트입니다. 각 요소는 0으로 초기화됩니다. `memblock`은 `NULL`이 아닌 경우 `calloc`, [malloc](../../c-runtime-library/reference/malloc.md) 또는 [realloc](../../c-runtime-library/reference/realloc.md)에 대한 이전 호출에서 반환된 포인터여야 합니다.  
  
 새 블록은 새 메모리 위치에 있을 수 있으므로, `_recalloc`에서 반환하는 포인터가 `memblock` 인수를 통해 전달되는 포인터임이 보장되지 않습니다.  
  
 메모리 할당이 실패하거나 요청된 메모리의 양이 `_HEAP_MAXREQ`를 초과하는 경우 `_recalloc`는 `errno`를 `ENOMEM`으로 설정합니다. 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 `recalloc`는 C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 함수를 사용하여 새 처리기 모드를 설정하기 위해 `realloc`를 호출합니다. 새 처리기 모드는 실패 시 `realloc`가 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지를 나타냅니다. 기본적으로 `realloc`는 메모리 할당 실패 시 새 처리기 루틴을 호출하지 않습니다. `_recalloc`가 메모리 할당에 실패한 경우 `realloc`이 `new` 연산자가 같은 이유로 실패했을 때 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음을  
  
```  
_set_new_mode(1)  
```  
  
 프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다.  
  
 응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 `_recalloc` 확인 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 `_recalloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h> 및 \<malloc.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [링크 옵션](../../c-runtime-library/link-options.md)
