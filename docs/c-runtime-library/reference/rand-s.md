---
title: rand_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- rand_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rand_s
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, cryptographically secure
- random numbers, generating
- rand_s function
- numbers, pseudorandom
- cryptographically secure random numbers
- pseudorandom numbers
- numbers, generating pseudorandom
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
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
ms.openlocfilehash: 5087948c5737f105e9bc694da1e866be659ff18f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="rands"></a>rand_s
의사 난수를 생성합니다. [rand](../../c-runtime-library/reference/rand.md) 버전은 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되는 경우 0이고 그렇지 않으면 오류 코드입니다. 입력 포인터 `randomValue`가 null 포인터인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 함수가 `EINVAL`를 반환하며 `errno`를 `EINVAL`로 설정합니다. 함수가 다른 이유로 하면 *`randomValue`가 0으로 설정됩니다.  
  
## <a name="remarks"></a>설명  
 `rand_s` 함수는 0부터 `UINT_MAX` 범위의 의사 난수 정수를 입력 포인터에 씁니다. `rand_s` 함수는 운영 체제를 사용하여 암호화된 보안 난수를 생성합니다. 이 함수는 [srand](../../c-runtime-library/reference/srand.md) 함수에서 생성한 시드를 사용하지 않으며, `rand`에서 사용하는 난수 시퀀스에도 영향을 주지 않습니다.  
  
 `rand_s` 함수에서는 다음 예제와 같이 선언하려는 함수의 포함문 앞에 상수 `_CRT_RAND_S`를 정의해야 합니다.  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s`는 [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) API에 따라 달라집니다(Windows XP 이상에서만 사용 가능함).  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`rand_s`|\<stdlib.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_rand_s.c  
// This program illustrates how to generate random  
// integer or floating point numbers in a specified range.  
  
// Remembering to define _CRT_RAND_S prior  
// to inclusion statement.  
#define _CRT_RAND_S  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <limits.h>  
  
int main( void )  
{  
    int             i;  
    unsigned int    number;  
    double          max = 100.0;  
    errno_t         err;  
  
    // Display 10 random integers in the range [ 1,10 ].  
    for( i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %u\n", (unsigned int) ((double)number /  
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);  
    }  
  
    printf_s("\n");  
  
    // Display 10 random doubles in [0, max).  
    for (i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %g\n", (double) number /   
                          ((double) UINT_MAX + 1) * max );  
    }  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
10  
4  
5  
2  
8  
2  
5  
6  
1  
1  
  
32.6617  
29.4471  
11.5413  
6.41924  
20.711  
60.2878  
61.0094  
20.1222  
80.9192  
65.0712  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)
