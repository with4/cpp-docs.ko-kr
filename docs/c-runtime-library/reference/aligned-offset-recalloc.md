---
title: "_aligned_offset_recalloc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84cf4f353d71cd5fc21957dc0ab9178982ad6030
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void * _aligned_offset_recalloc(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 현재 메모리 블록 포인터입니다.  
  
 `num`  
 요소의 수입니다.  
  
 `size`  
 각 요소의 길이입니다(바이트).  
  
 `alignment`  
 맞춤 값으로 2의 정수 거듭제곱이어야 합니다.  
  
 `offset`  
 맞춤을 강제하는 메모리 할당으로의 오프셋입니다.  
  
## <a name="return-value"></a>반환 값  
 `_aligned_offset_recalloc`는 다시 할당된(그리고 이동되었을 수 있는) 메모리 블록에 대한 void 포인터를 반환합니다. 크기가 0이고 버퍼 인수가 `NULL`이 아닌 경우 또는 버퍼를 지정된 크기로 확장하는 데 사용할 수 있는 메모리가 부족한 경우 반환 값은 `NULL`입니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.  
  
 `_aligned_offset_recalloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)와 마찬가지로 `_aligned_offset_recalloc`는 구조가 구조 내 오프셋에서 정렬될 수 있도록 합니다.  
  
 `_aligned_offset_recalloc`는 `malloc`를 기반으로 합니다. `_aligned_offset_malloc` 사용에 대한 자세한 내용은 [malloc](../../c-runtime-library/reference/malloc.md)를 참조하세요. `memblock`이 `NULL`인 경우 함수는 내부적으로 `_aligned_offset_malloc`를 호출합니다.  
  
 메모리 할당에 실패한 경우 또는 요청된 크기(`num` * `size`)가 `_HEAP_MAXREQ`보다 큰 경우 이 함수는 `errno`를 `ENOMEM`으로 설정합니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요. 또한 `_aligned_offset_recalloc`는 매개 변수의 유효성을 검사합니다. `alignment`가 2의 거듭제곱이 아니거나 `offset`이 요청된 크기와 같거나 크고 0이 아닌 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_aligned_offset_recalloc`|\<malloc.h>|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)   
 [_recalloc](../../c-runtime-library/reference/recalloc.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)