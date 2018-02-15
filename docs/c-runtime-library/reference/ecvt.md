---
title: "_ecvt | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ecvt
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
f1_keywords:
- _ecvt
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee37eb3623f27f4fb6883b2d16fc4c21c2a960c1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ecvt"></a>_ecvt
`double` 숫자를 문자열로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *_ecvt(   
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
 저장된 자릿수입니다.  
  
 `dec`  
 저장된 소수점 위치입니다.  
  
 `sign`  
 변환된 숫자의 부호입니다.  
  
## <a name="return-value"></a>반환 값  
 `_ecvt`는 숫자 문자열에 대한 포인터를 반환합니다. 오류가 발생한 경우 NULL입니다.  
  
## <a name="remarks"></a>설명  
 `_ecvt` 함수는 부동 소수점 숫자를 문자열로 변환합니다. `value` 매개 변수는 변환할 부동 소수점 숫자입니다. 이 함수는 `value` 중 최대 `count`개의 숫자를 문자열로 저장하고 null 문자('\0')를 추가합니다. `value`의 숫자 개수가 `count`개를 초과하면 낮은 자리 숫자가 반올림됩니다. 숫자가 `count`개보다 적으면 문자열이 0으로 채워집니다.  
  
 `_ecvt`에서 반환된 전체 숫자 개수는 `_CVTBUFSIZE`를 초과하지 않습니다.  
  
 숫자만 문자열에 저장됩니다. 소수점 위치와 `value`의 부호는 호출 후에 `dec` 및 `sign`에서 얻을 수 있습니다. `dec` 매개 변수는 문자열의 시작을 기준으로 소수점의 위치를 제공하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. `sign` 매개 변수는 변환된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.  
  
 `_ecvt`와 `_fcvt`의 차이는 `count` 매개 변수의 해석에 있습니다. `_ecvt`는 `count`를 출력 문자열의 전체 숫자 개수로 해석하는 반면, `_fcvt`는 `count`를 소수점 뒤의 자릿수로 해석합니다.  
  
 `_ecvt` 및 `_fcvt`는 정적으로 할당된 단일 버퍼를 변환에 사용합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `dec` 또는 `sign`이 NULL이거나 `count`가 0이면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `errno`는 `EINVAL`로 설정되고 NULL이 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)