---
title: "_fcvt | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords: _fcvt
dev_langs: C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c66666d615dc94f74f17736de6011ec05f1eeca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fcvt"></a>_fcvt
부동 소수점 숫자를 문자열로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *_fcvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value`  
 변환할 숫자입니다.  
  
 `count`  
 소수점 뒤의 자릿수입니다.  
  
 `dec`  
 저장된 소수점 위치의 포인터입니다.  
  
 `sign`  
 저장된 부호 표시기의 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `_fcvt`는 숫자 문자열에 대한 포인터를 반환합니다. 오류가 발생한 경우 NULL입니다.  
  
## <a name="remarks"></a>설명  
 `_fcvt` 함수는 부동 소수점 숫자를 null 종료 문자열로 변환합니다. `value` 매개 변수는 변환할 부동 소수점 숫자입니다. `_fcvt`는 `value` 중 숫자를 문자열로 저장하고 null 문자('\0')를 추가합니다. `count` 매개 변수는 소수점 뒤에 저장할 자릿수를 지정합니다. 나머지 숫자는 `count`자리로 반올림됩니다. 정밀도의 숫자가 `count`개보다 적으면 문자열이 0으로 채워집니다.  
  
 `_fcvt`에서 반환된 전체 숫자 개수는 `_CVTBUFSIZE`를 초과하지 않습니다.  
  
 숫자만 문자열에 저장됩니다. 소수점 위치와 `value`의 부호는 호출 후에 `dec` 및 sign에서 얻을 수 있습니다. `dec` 매개 변수는 문자열의 시작을 기준으로 소수점의 위치를 제공하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. 매개 변수 `sign`은 `value`의 부호를 나타내는 정수를 가리킵니다. `value`가 양수일 경우 정수가 0으로 설정되고 `value`가 음수일 경우 0이 아닌 숫자로 설정됩니다.  
  
 `_ecvt`와 `_fcvt`의 차이는 `count` 매개 변수의 해석에 있습니다. `_ecvt`는 `count`를 출력 문자열의 전체 숫자 개수로 해석하는 반면, `_fcvt`는 `count`를 소수점 뒤의 자릿수로 해석합니다.  
  
 `_ecvt` 및 `_fcvt`는 정적으로 할당된 단일 버퍼를 변환에 사용합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `dec` 또는 `sign`이 NULL이거나 `count`가 0이면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `errno`는 `EINVAL`로 설정되고 NULL이 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)