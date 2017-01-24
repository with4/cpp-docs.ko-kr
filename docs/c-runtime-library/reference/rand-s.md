---
title: "rand_s | Microsoft Docs"
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
  - "rand_s"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "rand_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "암호화 보안 난수"
  - "의사 난수 생성"
  - "숫자, 의사 난수 생성"
  - "숫자, 의사 난수"
  - "의사 난수"
  - "rand_s 함수"
  - "난수, 암호화 보안"
  - "난수, 생성"
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rand_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

의사 난수를 생성합니다.  [rand](../../c-runtime-library/reference/rand.md) 의 버젼은 보안 향상과 관련된[CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)로 설명됩니다.  
  
## 구문  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## 반환 값  
 성공하면 0이고, 그렇지 않으면 오류 코드입니다.  만일 입력 포인터 `randomValue` 가 null 포인터인 경우, 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 함수는 `EINVAL` 를 반환하고 `errno` 을 `EINVAL`으로 설정합니다.  만일 함수가 어떤 이유로 인해 실패한다면, \*`randomValue` 이 0으로 설정됩니다.  
  
## 설명  
 `rand_s` 함수는 범위 0에서 난수 정수를 입력 포인터에 `UINT_MAX` 로 씁니다.  `rand_s` 함수는 암호화된 보안 난수를 생성하기 위해 운영체제를 사용합니다.  이것은 [srand](../../c-runtime-library/reference/srand.md) 함수에 의해 생성된 시드를 사용하지 않고, 이것이 `rand` 에 의해 사용된 난수의 순서에 영향을 주지 않습니다.  
  
 `rand_s` 함수는 다음 예제처럼, 선언된 함수에 대한 이전 포함문이 정의되는 상수 `_CRT_RAND_S` 을 필요로 합니다.  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s` 는 [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) API에 따라 달라지며, 오직 Windows XP와 그 이후에 이용할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`rand_s`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 [](../../c-runtime-library/compatibility.md "Compatibility")을 참조하십시오.  
  
## 예제  
  
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
  
## 샘플 출력  
  
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
  
## 해당 .NET Framework 항목  
 [System::Random 클래스](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)