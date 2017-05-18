---
title: set_unexpected(CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- set_unexpected
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
f1_keywords:
- set_unexpected
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
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
ms.openlocfilehash: f71fbabf28c9e196a8cc0985e04bb2b39ab7ad93
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="setunexpected-crt"></a>set_unexpected(CRT)
`unexpected`로 호출하는 자체 종료 함수를 설치합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `unexpFunction`  
 `unexpected` 함수 대신 사용하기 위해 작성하는 함수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이전 함수를 나중에 복원할 수 있도록 `_set_unexpected`에서 등록한 이전 종료 함수에 대한 포인터를 반환합니다. 이전 함수가 설정되지 않은 경우 반환 값은 기본 동작을 복원하는 데 사용되며 이 값은 NULL일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `set_unexpected` 함수는 `unexpected`에서 호출한 함수로 `unexpFunction`을 설치합니다. `unexpected`는 현재 C++ 예외 처리 구현에서 사용되지 않습니다. `unexpected_function` 형식은 EH.H에서 `void`를 반환하는 사용자 정의 unexpected 함수 `unexpFunction`에 대한 포인터로 정의됩니다. 사용자 지정 `unexpFunction` 함수는 해당 호출자에게 반환되어서는 안 됩니다.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 기본적으로 `unexpected`는 `terminate`를 호출합니다. 종료 함수를 직접 작성하고 함수 이름을 인수로 사용해 `set_unexpected`를 호출하면 이 기본 동작을 변경할 수 있습니다. `unexpected`는 `set_unexpected`에 대한 인수로 지정된 마지막 함수를 호출합니다.  
  
 `set_terminate` 호출을 통해 설치한 사용자 지정 종료 함수와는 달리, `unexpFunction` 내에서 예외를 throw할 수 있습니다.  
  
 다중 스레드 환경에서 unexpected 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 unexpected 함수를 설치해야 합니다. 따라서 각 스레드는 자체 unexpected 처리를 담당합니다.  
  
 C++ 예외 처리의 현재 Microsoft 구현에서는 `unexpected`가 기본적으로 `terminate`를 호출하며 예외 처리 런타임 라이브러리를 통해서는 호출되지 않습니다. `terminate`가 아닌 `unexpected`를 호출하는 방식에 특별한 이점은 없습니다.  
  
 동적으로 연결된 모든 DLL 또는 EXE에 대해서는 `set_unexpected` 처리기가 1개 있습니다. `set_unexpected`를 호출하더라도 사용자의 처리기가 다른 처리기로 바뀌거나 사용자가 다른 DLL 또는 EXE로 설정한 처리기를 바꿀 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`set_unexpected`|\<eh.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
