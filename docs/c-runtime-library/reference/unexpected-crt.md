---
title: unexpected(CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: unexpected
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
f1_keywords: unexpected
dev_langs: C++
helpviewer_keywords: unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39cc7164a22b95f2c269c7bb1bd558374f56fa3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="unexpected-crt"></a>unexpected(CRT)
`terminate`를 사용하여 `set_unexpected` 또는 사용자가 지정하는 함수를 호출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void unexpected( void );  
```  
  
## <a name="remarks"></a>설명  
 `unexpected` 루틴은 C++ 예외 처리의 현재 구현과 함께 사용되지 않습니다. `unexpected`는 기본적으로 `terminate`를 호출합니다. 사용자는 사용자 지정 종료 함수를 작성하고 함수 이름과 함께 `set_unexpected`를 해당 인수로 호출하여 이 기본 동작을 변경할 수 있습니다. `unexpected`는 `set_unexpected`에 대한 인수로 지정된 마지막 함수를 호출합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`unexpected`|\<eh.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)