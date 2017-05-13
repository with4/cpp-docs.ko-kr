---
title: "_cexit, _c_exit | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _c_exit
- _cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
dev_langs:
- C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
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
ms.openlocfilehash: a68b803ee7dc444439d7a62f43cf7157e7fbf505
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="cexit-cexit"></a>_cexit, _c_exit
정리 작업을 수행하고 프로세스 종료 없이 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## <a name="remarks"></a>설명  
 `_cexit` 함수는 `atexit` 및 `_onexit`를 통해 등록된 함수를 LIFO(후입선출) 순서로 호출합니다. 그런 다음, `_cexit`는 반환하기 전에 모든 I/O 버퍼를 플러시하고 열려 있는 모든 스트림을 닫습니다. `_c_exit`는 `_exit`와 동일하지만, `atexit` 또는 `_onexit`를 처리하지 않거나 스트림 버퍼를 플러시하지 않고 호출 프로세스로 반환합니다. `exit`,`_exit`, `_cexit` 및 `_c_exit`의 동작은 다음 표에 나와 있습니다.  
  
|함수|동작|  
|--------------|--------------|  
|`exit`|전체 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드와 함께 종료됩니다.|  
|`_exit`|빠른 C 라이브러리 종료 절차를 수행하고, 프로세스를 종료하고, 제공된 상태 코드와 함께 종료됩니다.|  
|`_cexit`|전체 C 라이브러리 종료 절차를 수행하고 호출자에게 반환하지만, 프로세스를 종료하지 않습니다.|  
|`_c_exit`|빠른 C 라이브러리 종료 절차를 수행하고 호출자에게 반환하지만, 프로세스를 종료하지 않습니다.|  
  
 `_cexit` 또는 `_c_exit` 함수를 호출하는 경우 호출 당시에 존재하는 임시 또는 자동 개체에 대한 소멸자가 호출되지 않습니다. 자동 개체는 개체가 정적으로 선언되지 않은 함수에서 정의된 개체입니다. 임시 개체는 컴파일러에 의해 생성된 개체입니다. `_cexit` 또는 `_c_exit`를 호출하기 전에 자동 개체를 삭제하려면 다음과 같이 개체에 대한 소멸자를 명시적으로 호출합니다.  
  
```  
myObject.myClass::~myClass( );  
```  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_cexit`|\<process.h>|  
|`_c_exit`|\<process.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)
