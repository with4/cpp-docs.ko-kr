---
title: "_aligned_free | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_free
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
- aligned_free
- _aligned_free
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 8ddc662a1d497a419ebbaf0a93bfbf0ec17b664a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="alignedfree"></a>_aligned_free
[_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 `_aligned_malloc` 또는 `_aligned_offset_malloc` 함수로 반환된 메모리 블록에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_aligned_free`는 `__declspec(noalias)`로 표시되면 함수는 전역 변수를 수정하지 않도록 보장되지 않습니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.  
  
 이 함수는 다른 _aligned CRT 함수와 달리 매개 변수의 유효성을 검사하지 않습니다. `memblock`이 `NULL` 포인터인 경우 이 함수는 아무 작업도 수행하지 않습니다. `errno`를 변경하지 않으며, 잘못된 매개 변수 처리기를 호출하지도 않습니다. 메모리 블록을 할당하기 위해 전에 _aligned 함수를 사용하지 않아 함수에 오류가 발생하거나 예기치 않은 문제 때문에 메모리 맞춤 오류가 발생하면 함수는 [_RPT, _RPTF, _RPTW, _RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)에서 디버그 보고서를 생성합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_aligned_free`|\<malloc.h>|  
  
## <a name="example"></a>예제  
 자세한 내용은 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)
