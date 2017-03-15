---
title: "_onexit, _onexit_m | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_onexit"
  - "_onexit_m"
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
  - "_onexit"
  - "onexit_m"
  - "onexit"
  - "_onexit_m"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "onexit 함수"
  - "레지스트리, 종료 루틴 등록"
  - "_onexit_m 함수"
  - "onexit_m 함수"
  - "_onexit 함수"
  - "종료 루틴 등록"
  - "종료 시 호출되도록 등록"
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _onexit, _onexit_m
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

종료 시 호출 되는 루틴을 등록 합니다.  
  
## 구문  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### 매개 변수  
 `function`  
 종료할 때 호출 되는 함수에 대한 포인터입니다.  
  
## 반환 값  
 `_onexit` 는 성공하거나 `NULL` 인 경우, 함수 포인터를 저장할 공간이 없는 경우, 함수에 대한 포인터를 반환합니다.  
  
## 설명  
 프로그램이 정상적으로 종료될 때 함수 `_onexit`은 함수 `function`의 주소로써 전달됩니다.  `_onexit`에 대한 연속적인 호출은 후입선출\(LIFO\) 순서대로 실행되는 함수 레지스터를 생성합니다.  `_onexit`로 전달된 함수는 매개 변수를 사용할 수 없습니다.  
  
 `_onexit` 이 DLL 내에서 호출된 경우, `_onexit` 를 사용해 등록된 루틴은 `DllMain` 가 DLL\_PROCESS\_DETACH 를 사용하여 호출된 이후 DLL의 언로드를 실행합니다.  
  
 `_onexit`은 Microsoft 확장입니다.  ANSI 이식성에 대해 [atexit](../../c-runtime-library/reference/atexit.md) 를 사용하십시오.  이 함수의 `_onexit_m` 버전은 혼합된 모드 사용입니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_onexit`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
## Output  
  
```  
This is executed first.  
This is executed next.  
```  
  
## 해당 .NET Framework 항목  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_\_dllonexit](../../c-runtime-library/dllonexit.md)