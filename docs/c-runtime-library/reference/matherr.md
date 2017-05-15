---
title: "_matherr | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _matherr
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
- _matherr
- matherr
dev_langs:
- C++
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
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
ms.openlocfilehash: 20ed6b9111e7dc3a25462ea9d8b79b8e9e842ed0
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="matherr"></a>_matherr
수학 오류를 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *except*  
 오류 정보를 포함하는 구조에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 _**matherr**은 오류를 나타내기 위해 0을 반환하거나 성공을 나타내기 위해 0이 아닌 값을 반환합니다. \_**matherr**이 0을 반환하면 오류 메시지가 표시될 수 있으며 `errno`가 적절한 오류 값으로 설정됩니다. \_**matherr**이 0이 아닌 값을 반환하면 오류 메시지가 표시되지 않으며 `errno`가 변경되지 않습니다.  
  
 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 _**matherr** 함수는 수학 라이브러리의 부동 소수점 함수에 의해 생성되는 오류를 처리합니다. 이러한 함수는 오류가 발견되면 \_**matherr**을 호출합니다.  
  
 특별 오류 처리를 위해 _**matherr**의 다른 정의를 제공할 수 있습니다. C 런타임 라이브러리의 동적 연결 버전(Msvcr90.dll)을 사용하는 경우 클라이언트 실행 파일에서 기본 \_**matherr** 루틴을 사용자 정의 버전으로 대체할 수 있습니다. 그러나 Msvcr90.dll의 DLL 클라이언트에서 기본 `_matherr` 루틴을 대체할 수는 없습니다.  
  
 수학 루틴에서 오류가 발생하면 **_exception** 형식 구조체(Math.h에 정의됨)에 대한 포인터를 인수로 사용하여 _**matherr**이 호출됩니다. **_exception** 구조체에는 다음 요소가 포함되어 있습니다.  
  
 **int type**  
 예외 형식입니다.  
  
 **char \*name**  
 오류가 발생한 함수의 이름입니다.  
  
 **double arg1**, **arg2**  
 함수에 대한 첫 번째 및 두 번째(있는 경우) 인수입니다.  
  
 **double retval**  
 함수에 의해 반환될 값입니다.  
  
 **type**은 수학 오류의 형식을 지정하며, Math.h에 정의된 다음 값 중 하나입니다.  
  
 `_DOMAIN`  
 인수 도메인 오류입니다.  
  
 `_SING`  
 인수 특이성입니다.  
  
 `_OVERFLOW`  
 오버플로 범위 오류입니다.  
  
 `_PLOSS`  
 중요성의 부분적 손실입니다.  
  
 `_TLOSS`  
 중요성의 전체 손실입니다.  
  
 `_UNDERFLOW`  
 결과가 너무 작아 나타낼 수 없습니다. 이 조건은 현재 지원되지 않습니다.  
  
 구조체 멤버 **name**은 오류를 발생시킨 함수의 이름을 포함하는 null로 종료되는 문자열에 대한 포인터입니다. 구조체 멤버 **arg1** 및 **arg2**는 오류를 발생시킨 값을 지정합니다. 인수가 하나만 지정된 경우 **arg1**에 저장됩니다.  
  
 지정된 오류의 기본 반환 값은 **retval**입니다. 반환 값을 변경하는 경우 오류가 실제로 발생했는지 여부를 해당 값이 지정해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_matherr`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="output"></a>출력  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
