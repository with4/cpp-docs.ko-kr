---
title: "div | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- div
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
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
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
ms.openlocfilehash: e1e92656713a31d3057dfe180bd1cb4e819ceb5b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="div"></a>div
두 정수 값의 몫과 나머지를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### <a name="parameters"></a>매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
## <a name="return-value"></a>반환 값  
 `div` 형식의 인수를 사용하여 호출된 `int`는 몫과 나머지로 구성된 `div_t` 형식의 구조체를 반환합니다. `long` 형식의 인수를 사용하는 오버로드의 반환 값은 `ldiv_t`입니다. `div_t` 및 `ldiv_t` 모두 STDLIB.H.에서 정의됩니다.  
  
## <a name="remarks"></a>설명  
 `div` 함수는 `numer`를 `denom`으로 나눠서 몫과 나머지를 계산합니다. [div_t](../../c-runtime-library/standard-types.md) 구조체에는 목인 `int quot` 및 나머지인 `int rem`이 포함됩니다. 몫의 부호는 수학적 몫의 부호와 같습니다. 몫의 절대 값은 수학적 몫의 절대 값보다 작은 가장 큰 정수입니다. 분모가 0이면 프로그램이 종료되고 오류 메시지가 표시됩니다.  
  
 `long` 또는 `long long` 형식의 인수를 받는 오버로드는 C++ 코드에서만 사용할 수 있습니다. 반환 형식 [ldiv_t](../../c-runtime-library/standard-types.md)에는 멤버 `long quot` 및 `long rem`이 포함되고, 반환 형식 [lldiv_t](../../c-runtime-library/standard-types.md)에는 `div_t`의 멤버와 같은 의미를 가지는 멤버 `long long quot` 및 `long long rem`이 포함됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`div`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
```Output  
x is 876, y is 13  
The quotient is 67, and the remainder is 5  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)
