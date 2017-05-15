---
title: _query_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_mode
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
- query_new_mode
- _query_new_mode
dev_langs:
- C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 414bbd73f44a51ab1ec35c9fb2bd8b3914c1ea8d
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="querynewmode"></a>_query_new_mode
`malloc`에 대해 `_set_new_mode`에서 설정한 새 처리기 모드를 나타내는 정수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## <a name="return-value"></a>반환 값  
 `malloc`에 대해 현재 새 처리기 모드(0 또는 1)를 반환합니다. 반환 값이 1이면 메모리 할당이 실패하는 경우 `malloc`가 새 처리기 루틴을 호출함을 나타내며, 반환 값이 0이면 해당 루틴을 호출하지 않음을 나타냅니다.  
  
## <a name="remarks"></a>설명  
 C++ `_query_new_mode` 함수는 [malloc](../../c-runtime-library/reference/malloc.md)에 대해 C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 함수에서 설정하는 새 처리기 모드를 나타내는 정수를 반환합니다. 새 처리기 모드는 메모리 할당이 실패하는 경우 `malloc`가 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지를 나타냅니다. 기본적으로 `malloc`는 실패 시에 새 처리기 루틴을 호출하지 않습니다. `_set_new_mode`를 사용하면 메모리 할당 실패 시에 **new** 연산자와 같은 방식으로 `malloc`가 새 처리기 루틴을 호출하도록 이 동작을 재정의할 수 있습니다. 자세한 내용은 C++ 언어 참조의 [new 및 delete 연산자](../../cpp/new-and-delete-operators.md)에 대한 설명을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_query_new_mode`|\<new.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)
