---
title: quick_exit1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: quick_exit
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
f1_keywords:
- quick_exit
- process/quick_exit
- stdlib/quick_exit
dev_langs: C++
helpviewer_keywords: quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb6a8bdea6cb37bd70d6aeda490e2470aa74e999
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="quickexit"></a>quick_exit
프로그램이 정상 종료되게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
__declspec(noreturn) void quick_exit(  
    int status  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 status  
 호스트 환경에 반환될 상태 코드입니다.  
  
## <a name="return-value"></a>반환 값  
 `quick_exit` 함수는 호출자로 돌아갈 수 없습니다.  
  
## <a name="remarks"></a>설명  
 `quick_exit` 함수를 사용하면 프로그램이 정상 종료됩니다. `atexit`, `_onexit` 를 통해 등록된 함수 또는 `signal` 함수를 통해 등록된 신호 처리기가 호출되지 않습니다. `quick_exit` 가 두 번 이상 호출되거나 `exit` 함수도 호출되면 동작이 정의되지 않습니다.  
  
 `quick_exit` 함수는 함수가 등록될 때 이미 호출된 함수를 제외하고 `at_quick_exit`를 통해 등록된 함수를 LIFO(후입선출) 순서로 호출합니다.  함수 호출을 종료하는 등록된 함수를 호출하는 동안 [longjmp](../../c-runtime-library/reference/longjmp.md) 가 호출되면 동작이 정의되지 않습니다.  
  
 등록된 함수가 호출된 후 `quick_exit` 는 `_Exit` 값을 사용하여 제어를 호스트 환경으로 반환하는 방식으로 `status` 를 호출합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`quick_exit`|\<process.h> 또는 \<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)