---
title: "_aligned_offset_realloc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
dev_langs: C++
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9108ddc65fb7728bbb78b3002bad21ce9597f7c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="alignedoffsetrealloc"></a>_aligned_offset_realloc
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void * _aligned_offset_realloc(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   size_t offset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 현재 메모리 블록 포인터입니다.  
  
 `size`  
 메모리 할당의 크기입니다.  
  
 `alignment`  
 2의 정수 제곱이어야 하는 맞춤 값입니다.  
  
 `offset`  
 맞춤을 강제하는 메모리 할당으로의 오프셋입니다.  
  
## <a name="return-value"></a>반환 값  
 `_aligned_offset_realloc`는 다시 할당된(그리고 이동되었을 수 있는) 메모리 블록에 대한 void 포인터를 반환합니다. 크기가 0이고 버퍼 인수가 `NULL`이 아닌 경우 또는 버퍼를 지정된 크기로 확장하는 데 사용할 수 있는 메모리가 부족한 경우 반환 값은 `NULL`입니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.  
  
 `_aligned_offset_realloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)와 마찬가지로 `_aligned_offset_realloc`는 구조가 구조 내 오프셋에서 정렬될 수 있도록 합니다.  
  
 `_aligned_offset_realloc`는 `malloc`를 기반으로 합니다. `_aligned_offset_malloc` 사용에 대한 자세한 내용은 [malloc](../../c-runtime-library/reference/malloc.md)를 참조하세요. `memblock`이 `NULL`인 경우 함수는 내부적으로 `_aligned_offset_malloc`를 호출합니다.  
  
 이 함수는 메모리 할당에 실패한 경우 또는 요청된 크기가 `errno`보다 큰 경우 `ENOMEM`를 `_HEAP_MAXREQ`으로 설정합니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요. 또한 `_aligned_offset_realloc`는 매개 변수의 유효성을 검사합니다. `alignment`가 2의 거듭제곱이 아니거나 `offset`이 `size`와 같거나 크고 0이 아닌 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `NULL`을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_aligned_offset_realloc`|\<malloc.h>|  
  
## <a name="example"></a>예  
 자세한 내용은 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)