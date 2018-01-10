---
title: set_terminate(CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords: set_terminate
dev_langs: C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 099cb340f821f04c3a5f84ccef7e3e9649482cd6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setterminate-crt"></a>set_terminate(CRT)
`terminate`로 호출할 자체 종료 루틴을 설치합니다.  
  
## <a name="syntax"></a>구문  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `termFunction`  
 작성하는 terminate 함수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이전 함수를 나중에 복원할 수 있도록 `set_terminate`에서 등록한 이전 함수에 대한 포인터를 반환합니다. 이전 함수가 설정되지 않은 경우 반환 값은 기본 동작을 복원하는 데 사용되며 이 값은 NULL일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `set_terminate` 함수는 `terminate`에서 호출한 함수로 `termFunction`을 설치합니다. `set_terminate`는 C++ 예외 처리와 함께 사용되며, 예외가 throw되기 전에 프로그램의 어떤 지점에서든 호출할 수 있습니다. `terminate`는 기본적으로 `abort`를 호출합니다. 종료 함수를 직접 작성하고 함수 이름을 인수로 사용해 `set_terminate`를 호출하면 이 기본값을 변경할 수 있습니다. `terminate`는 `set_terminate`에 대한 인수로 지정된 마지막 함수를 호출합니다. 원하는 정리 작업을 수행한 후에는 `termFunction`이 프로그램을 종료해야 합니다. 프로그램이 종료되지 않고 호출자에게 반환되는 경우에는 `abort`가 호출됩니다.  
  
 다중 스레드 환경에서 terminate 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 terminate 함수를 설치해야 합니다. 따라서 각 스레드는 자체 종료 처리를 담당합니다.  
  
 `terminate_function` 형식은 EH.H에서 `void`를 반환하는 사용자 정의 종료 함수 `termFunction`에 대한 포인터로 정의됩니다. 사용자 지정 함수 `termFunction`은 인수를 사용할 수 없으며 호출자에게 반환되어서는 안 됩니다. 이 함수가 호출자에게 반환되는 경우에는 `abort`가 호출됩니다. `termFunction` 내에서 예외가 throw되면 안 됩니다.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  `set_terminate` 함수는 디버거 외부에서만 작동합니다.  
  
 동적으로 연결된 모든 DLL 또는 EXE에 대해서는 `set_terminate` 처리기가 1개 있습니다. `set_terminate`를 호출하더라도 사용자의 처리기가 다른 처리기로 바뀌거나 사용자가 다른 DLL 또는 EXE로 설정한 처리기를 바꿀 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`set_terminate`|\<eh.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 [terminate](../../c-runtime-library/reference/terminate-crt.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)