---
title: "atexit | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atexit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "atexit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "atexit 함수"
  - "처리, 종료 시"
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atexit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

종료할 때 지정된 함수를 처리합니다.  
  
## 구문  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### 매개 변수  
 `func`  
 호출된 함수입니다.  
  
## 반환 값  
 `atexit`은 성공한 경우 0을, 오류가 발생한 경우 0이 아닌 값을 반환합니다.  
  
## 설명  
 프로그램이 정상적으로 종료될 때 함수 `atexit`은 함수 `func`의 주소로써 전달됩니다.  `atexit`에 대한 연속적인 호출은 후입선출\(LIFO\) 순서대로 실행되는 함수 레지스터를 생성합니다.  `atexit`로 전달된 함수는 매개 변수를 사용할 수 없습니다.  `atexit` 및 `_onexit`는 함수들의 레지스터를 유지하기 위해 힙을 사용합니다.  따라서, 등록할 수 있는 함수의 수는 힙 메모리에 의해서만 제한됩니다.  
  
 `atexit` 함수의 코드는 `atexit` 함수가 호출되었을 때 이미 언로드되었을 수 있는 모든 DLL에 대해 어떤 의존성도 포함하지 않아야 합니다.  
  
 ANSI 호환 응용 프로그램을 생성하기 위해서, ANSI 표준 `atexit` 함수\(유사한 `_onexit` 함수보다는\)를 사용하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`atexit`|\<stdlib.h\>|  
  
## 예제  
 이 프로그램은 `atexit`가 호출되었을 때 실행되는 함수의 스택에 네 개의 함수를 넣습니다.  프로그램이 종료될 때, 이러한 프로그램들이 후입선출 기반에서 실행됩니다.  
  
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
  
  **이 작업은 먼저 실행됩니다.**  
**이 작업은 다음으로 실행됩니다.**   
## 해당 .NET Framework 항목  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)