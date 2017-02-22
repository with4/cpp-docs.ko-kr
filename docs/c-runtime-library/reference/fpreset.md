---
title: "_fpreset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpreset"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fpreset"
  - "fpreset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fpreset 함수"
  - "부동 소수점 숫자, 수학 패키지 다시 설정"
  - "fpreset 함수"
ms.assetid: f31c6a04-b464-4f07-a7c4-42133360e328
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _fpreset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 패키지를 다시 설정합니다.  
  
## 구문  
  
```  
void _fpreset( void );  
```  
  
## 설명  
 이 `_fpreset` 함수는 부동 소수점 연산 패키지를 다시 초기화 합니다.  `_fpreset` 는 보통 `signal`, `system`, 또는 `_exec` 또는 `_spawn` 함수로 사용됩니다.  만일 프로그램 부동 소수점 오류 신호를 포착 하는 경우 \(`SIGFPE`\) `signal`를 사용합니다. 이는 부동 소수점 오류인 `_fpreset` 를 호출하고 `longjmp` 를 사용함으로써, 안전하게 복구할 수 있습니다.  
  
 공용 언어 런타임은 오직 기본 부동 소수점 정밀도만을 지원하기 때문에 이러한 함수는 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 또는 `/clr:pure` 를 사용하여 컴파일하는 경우 무시됩니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_fpreset`|\<float.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fpreset.c  
// This program uses signal to set up a  
// routine for handling floating-point errors.  
  
#include <stdio.h>  
#include <signal.h>  
#include <setjmp.h>  
#include <stdlib.h>  
#include <float.h>  
#include <math.h>  
#include <string.h>  
  
jmp_buf mark;              // Address for long jump to jump to  
int     fperr;             // Global error number  
  
void __cdecl fphandler( int sig, int num );   // Prototypes  
void fpcheck( void );  
  
int main( void )  
{  
   double n1 = 5.0;  
   double n2 = 0.0;  
   double r;  
   int jmpret;  
  
   // Unmask all floating-point exceptions.   
    _control87( 0, _MCW_EM );  
   // Set up floating-point error handler. The compiler  
   // will generate a warning because it expects  
   // signal-handling functions to take only one argument.  
   if( signal( SIGFPE, (void (__cdecl *)(int)) fphandler ) == SIG_ERR )  
    {  
       fprintf( stderr, "Couldn't set SIGFPE\n" );  
       abort();  
    }  
  
   // Save stack environment for return in case of error. First   
   // time through, jmpret is 0, so true conditional is executed.   
   // If an error occurs, jmpret will be set to -1 and false   
   // conditional will be executed.  
   jmpret = setjmp( mark );  
   if( jmpret == 0 )  
   {  
      printf( "Dividing %4.3g by %4.3g...\n", n1, n2 );  
      r = n1 / n2;  
      // This won't be reached if error occurs.  
      printf( "\n\n%4.3g / %4.3g = %4.3g\n", n1, n2, r );  
  
      r = n1 * n2;  
      // This won't be reached if error occurs.  
      printf( "\n\n%4.3g * %4.3g = %4.3g\n", n1, n2, r );  
   }  
   else  
      fpcheck();  
}  
// fphandler handles SIGFPE (floating-point error) interrupt. Note  
// that this prototype accepts two arguments and that the   
// prototype for signal in the run-time library expects a signal   
// handler to have only one argument.  
//  
// The second argument in this signal handler allows processing of  
// _FPE_INVALID, _FPE_OVERFLOW, _FPE_UNDERFLOW, and   
// _FPE_ZERODIVIDE, all of which are Microsoft-specific symbols   
// that augment the information provided by SIGFPE. The compiler   
// will generate a warning, which is harmless and expected.  
  
void fphandler( int sig, int num )  
{  
   // Set global for outside check since we don't want  
   // to do I/O in the handler.  
   fperr = num;  
  
   // Initialize floating-point package. */  
   _fpreset();  
  
   // Restore calling environment and jump back to setjmp. Return   
   // -1 so that setjmp will return false for conditional test.  
   longjmp( mark, -1 );  
}  
  
void fpcheck( void )  
{  
   char fpstr[30];  
   switch( fperr )  
   {  
   case _FPE_INVALID:  
       strcpy_s( fpstr, sizeof(fpstr), "Invalid number" );  
       break;  
   case _FPE_OVERFLOW:  
       strcpy_s( fpstr, sizeof(fpstr), "Overflow" );  
  
       break;  
   case _FPE_UNDERFLOW:  
       strcpy_s( fpstr, sizeof(fpstr), "Underflow" );  
       break;  
   case _FPE_ZERODIVIDE:  
       strcpy_s( fpstr, sizeof(fpstr), "Divide by zero" );  
       break;  
   default:  
       strcpy_s( fpstr, sizeof(fpstr), "Other floating point error" );  
       break;  
   }  
   printf( "Error %d: %s\n", fperr, fpstr );  
}  
```  
  
  **5를 0으로 나눕니다.**  
**0으로 나누기 오류 131:**   
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_exec, \_wexec 함수](../../c-runtime-library/exec-wexec-functions.md)   
 [신호](../../c-runtime-library/reference/signal.md)   
 [\_spawn, \_wspawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)