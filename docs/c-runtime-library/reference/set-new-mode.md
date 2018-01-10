---
title: _set_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_new_mode
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
- set_new_mode
- _set_new_mode
dev_langs: C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 31fb5217c70c41e633fffc69cd05624366fa29eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setnewmode"></a>_set_new_mode
`malloc`에 대해 새 처리기 모드를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `newhandlermode`  
 `malloc`에 대한 새 처리기 모드입니다. 유효한 값은 0 또는 1입니다.  
  
## <a name="return-value"></a>반환 값  
 `malloc`에 대해 설정된 이전 처리기 모드를 반환합니다. 반환 값이 1이면 메모리 할당이 실패하는 경우 `malloc`가 이전에 새 처리기 루틴을 호출했음을 나타내며, 반환 값이 0이면 해당 루틴을 호출하지 않았음을 나타냅니다. 경우는 `newhandlermode` 인수는 0 또는 1 같지 않음,-1을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 C++ `_set_new_mode` 함수는 [malloc](../../c-runtime-library/reference/malloc.md)에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드는 실패 시 `malloc`가 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지를 나타냅니다. 기본적으로 `malloc`는 메모리 할당 실패 시 새 처리기 루틴을 호출하지 않습니다. `malloc`가 메모리 할당에 실패한 경우 `malloc`가 `new` 연산자가 같은 이유로 실패했을 때 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 자세한 내용은 *C++ 언어 참조*의 [new](../../cpp/new-operator-cpp.md) 및 [delete](../../cpp/delete-operator-cpp.md) 연산자를 참조하세요. 기본값을 재정의하려면 다음을  
  
```  
_set_new_mode(1)  
```  
  
 프로그램에서 초기에 호출하거나, Newmode.obj를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `newhandlermode`이 0 또는 1 이외의 값인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 **_**`set_new_mode`는 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)