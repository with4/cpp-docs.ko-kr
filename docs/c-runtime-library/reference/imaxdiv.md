---
title: "imaxdiv | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- imaxdiv
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
- imaxdiv
dev_langs:
- C++
helpviewer_keywords:
- imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 1d86597d8ff759a1a388fea785ff864d47c823ae
ms.lasthandoff: 02/24/2017

---
# <a name="imaxdiv"></a>imaxdiv
크기와 관계없이 한 번의 연산으로 두 정수 값의 몫과 나머지를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
imaxdiv_t imaxdiv(   
   intmax_t numer,  
   intmax_t denom   
);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
## <a name="return-value"></a>반환 값  
 [intmax_t](../../c-runtime-library/standard-types.md) 형식의 인수를 사용하여 호출된 `imaxdiv`는 몫과 나머지를 구성하는 [imaxdiv_t](../../c-runtime-library/standard-types.md) 형식의 구조체를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `imaxdiv` 함수는 `numer`를 `denom`으로 나눠서 몫과 나머지를 계산합니다. `imaxdiv_t` 구조체에는 몫인 `intmax_t``quot`와 나머지인 `intmax_t``rem`이 포함됩니다. 몫의 부호는 수학적 몫의 부호와 같습니다. 몫의 절대 값은 수학적 몫의 절대 값보다 작은 가장 큰 정수입니다. 분모가 0이면 프로그램이 종료되고 오류 메시지가 표시됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`imaxdiv`|\<inttypes.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_imaxdiv.c  
// Build using: cl /W3 /Tc crt_imaxdiv.c  
// This example takes two integers as command-line  
// arguments and calls imaxdiv to divide the first   
// argument by the second, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x,y;  
   imaxdiv_t div_result;  
  
   x = atoll(argv[1]);  
   y = atoll(argv[2]);  
  
   printf("The call to imaxdiv(%lld, %lld)\n", x, y);  
   div_result = imaxdiv(x, y);  
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",  
          div_result.quot, div_result.rem);  
}  
```  
  
 `9460730470000000 8766`의 명령줄 매개 변수를 사용하여 빌드된 다음 호출되면 코드는 다음 출력을 생성합니다.  
  
```Output  
The call to imaxdiv(9460730470000000, 8766)  
results in a quotient of 1079252848505, and a remainder of 5170  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)
