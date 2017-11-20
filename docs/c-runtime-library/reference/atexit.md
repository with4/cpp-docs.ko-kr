---
title: "atexit | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: atexit
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
f1_keywords: atexit
dev_langs: C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a385ebeba2d9dd58b59df179884f7add02b03a42
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="atexit"></a>atexit
종료 시 지정된 함수를 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `func`  
 호출할 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 `atexit`는 성공 시 0을 반환하고, 오류 발생 시 0이 아닌 값을 반환합니다.  
  
## <a name="remarks"></a>설명  
 프로그램이 정상적으로 종료될 때 `atexit` 함수에 호출될 함수의 주소(`func`)가 전달됩니다. `atexit`를 연속적으로 호출하면 LIFO(후입선출) 순서대로 실행되는 함수의 레지스터가 만들어집니다. `atexit`에 전달된 함수는 매개 변수를 사용할 수 없습니다. `atexit` 및 `_onexit`는 힙을 사용하여 함수의 레지스터를 저장합니다. 따라서 등록 가능한 함수의 수는 힙 메모리에 의해서만 제한됩니다.  
  
 `atexit` 함수의 코드는 `atexit` 함수 호출 시 이미 언로드되었을 수 있는 DLL에 대한 종속성을 포함해서는 안 됩니다.  
  
 ANSI 호환 응용 프로그램을 생성하려면 유사한 `_onexit` 함수보다는 ANSI 표준 `atexit` 함수를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`atexit`|\<stdlib.h>|  
  
## <a name="example"></a>예제  
 이 프로그램은 `atexit` 호출 시 실행할 함수 스택에 4개의 함수를 푸시합니다. 프로그램이 종료되면 LIFO(후입선출) 방식으로 이러한 프로그램이 실행됩니다.  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
```Output  
This is executed first.  
This is executed next.  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)