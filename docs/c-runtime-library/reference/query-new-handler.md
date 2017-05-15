---
title: _query_new_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _query_new_handler
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
- _query_new_handler
- query_new_handler
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
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
ms.openlocfilehash: 63d43e80009b0d6c8f2d827f6ea5b239d7a39663
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="querynewhandler"></a>_query_new_handler
현재 새 처리기 루틴의 주소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_PNH _query_new_handler(  
   void   
);  
```  
  
## <a name="return-value"></a>반환 값  
 `_set_new_handler`에서 설정한 대로 현재 새 처리기 루틴의 주소를 반환합니다.  
  
## <a name="remarks"></a>설명  
 C++ `_query_new_handler` 함수는 C++ [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) 함수로 설정한 현재 예외 처리 함수의 주소를 반환합니다. `_set_new_handler`는 **new** 연산자가 메모리를 할당하지 못한 경우 제어권을 얻는 예외 처리 함수를 지정하는 데 사용됩니다. 자세한 내용은 C++ 언어 참조의 [new 및 delete 연산자](../../cpp/new-and-delete-operators.md)에 대한 설명을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_query_new_handler`|\<new.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)
