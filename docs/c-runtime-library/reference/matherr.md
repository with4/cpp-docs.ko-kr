---
title: "_matherr | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_matherr"
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
  - "_matherr"
  - "matherr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_matherr 함수"
  - "matherr 함수"
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _matherr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

수학적 오류들을 처리합니다.  
  
## 구문  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### 매개 변수  
 *except*  
 오류 정보를 포함하는 구조체에 대한 포인터입니다.  
  
## 반환 값  
 \_**matherr** 성공임을 나타내기 위해 0이 아닌 값, 혹은 오류를 나타내기 위해 0을 반환합니다.  만일 \_**matherr** 가 0을 반환하면, 오류 메시지는 표시될 수 있고 `errno` 는 적합한 오류 값으로 설정됩니다.  만일 \_**matherr** 이 0이 아닌 값을 반환하는 경우, 오류메시지가 표시되지 않고 `errno` 는 변경되지 않습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 \_**Matherr** 함수는 math라이브러리의 부동 소수점에 의해 생성된 오류를 처리합니다.  이러한 함수는 오류가 발견된 경우 \_**matherr** 을 호출합니다.  
  
 특별한 오류 처리에 대해, **matherr** 의 다른 정의를 제공할 수 있습니다.  만일 C런타임 라이브러리\(Msvcr90.dll\)의 동적으로 연결된 버전을 사용하는 경우, 사용자 정의 버전을 사용하여 클라이언트 실행 파일에서 기본 \_**matherr** 루틴을 대체할 수 있습니다.  그러나, Msvcr90.dll 의 DLL 클라이언트에서 기본 `_matherr` 으로 대체할 수 없습니다.  
  
 math 루틴에서 오류가 발생할 때, **matherr** 는 매개변수로 **\_exception** 형식 구조\(Math.h에서 정의된\)에 대한 포인터를 사용하여 호출됩니다.  이 **exception**구조체에는 다음 요소가 포함되어 있습니다.  
  
 **int 형식**  
 Exception 형식.  
  
 **char \*name**  
 오류가 발생한 함수의 이름입니다.  
  
 **double arg1**, **arg2**  
 함수에 대한 첫 번째와 두 번째\(있는 경우\)인수들 입니다.  
  
 **double retval**  
 함수로 반환되는 값입니다.  
  
 **형식** 은 math 오류의 형식을 지정합니다.  이것은 다음 값의 하나이고, Math.h에서 정의됩니다.  
  
 `_DOMAIN`  
 인수 도메인 오류입니다.  
  
 `_SING`  
 인수 특이성.  
  
 `_OVERFLOW`  
 오버플로우 범위 오류입니다.  
  
 `_PLOSS`  
 의미의 부분적인 손실입니다.  
  
 `_TLOSS`  
 의미의 전체 손실입니다.  
  
 `_UNDERFLOW`  
 결과가 너무 작아 나타낼 수 없습니다. \(현재 이 조건이 지원되지 않는 경우.\)  
  
 구조체 멤버 **name** 은 오류를 야기하는 함수의 이름을 포함하는 null로 끝나는 문자열에 대한 포인터입니다.  구조체 멤버 **arg1** 와 **arg2** 는 오류를 발생시키는 값을 지정합니다. \(반일 오직 한개의 매개변수만 주어졌다면, 이것은 **arg1**에 저장됩니다.\)  
  
 주어진 오류에 대한 기본 반환값은 **retval**입니다.  만일 반환값이 변경되면, 오류가 실제로 발생했는지 여부를 지정해야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_matherr`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_matherr.c  
/* illustrates writing an error routine for math   
 * functions. The error function must be:  
 *      _matherr  
 */  
  
#include <math.h>  
#include <string.h>  
#include <stdio.h>  
  
int main()  
{  
    /* Do several math operations that cause errors. The _matherr  
     * routine handles _DOMAIN errors, but lets the system handle  
     * other errors normally.  
     */  
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );  
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );  
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );  
}  
  
/* Handle several math errors caused by passing a negative argument  
 * to log or log10 (_DOMAIN errors). When this happens, _matherr  
 * returns the natural or base-10 logarithm of the absolute value  
 * of the argument and suppresses the usual error message.  
 */  
int _matherr( struct _exception *except )  
{  
    /* Handle _DOMAIN errors for log or log10. */  
    if( except->type == _DOMAIN )  
    {  
        if( strcmp( except->name, "log" ) == 0 )  
        {  
            except->retval = log( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
        else if( strcmp( except->name, "log10" ) == 0 )  
        {  
            except->retval = log10( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
    }  
    printf( "Normal: " );  
    return 0;    /* Else use the default actions */  
}  
```  
  
## Output  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)