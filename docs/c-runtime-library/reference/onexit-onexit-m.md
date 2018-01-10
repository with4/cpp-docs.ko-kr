---
title: _onexit, _onexit_m | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
dev_langs: C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 476df668657739c9f67ca1323c2c0ce630260110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m
종료 시 호출할 루틴을 등록합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `function`  
 종료 시 호출할 함수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `_onexit`은 성공하는 경우 함수에 대한 포인터를 반환하고, 함수 포인터를 저장할 공간이 없는 경우 `NULL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 프로그램이 정상적으로 종료될 때 `_onexit` 함수에 호출될 함수의 주소(`function`)가 전달됩니다. `_onexit`을 연속적으로 호출하면 LIFO(후입선출) 순서대로 실행되는 함수의 레지스터가 만들어집니다. `_onexit`에 전달된 함수는 매개 변수를 사용할 수 없습니다.  
  
 DLL 내에서 `_onexit`이 호출되는 경우 DLL_PROCESS_DETACH를 사용하여 `_onexit`이 호출된 이후 DLL의 언로드에서 `DllMain`에 등록된 루틴이 실행됩니다.  
  
 `_onexit`는 Microsoft 확장입니다. ANSI 이식성이 필요한 경우에는 [atexit](../../c-runtime-library/reference/atexit.md)을 사용하세요. 이 함수의 `_onexit_m` 버전은 혼합된 모드용입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_onexit`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## <a name="output"></a>출력  
  
```  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [__dllonexit](../../c-runtime-library/dllonexit.md)