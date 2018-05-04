---
title: _fcvt | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fcvt
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
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fefe9bbfc1904847af5594a4d663b1eb8299fc9b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fcvt"></a>_fcvt

부동 소수점 숫자를 문자열로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [_fcvt_s](fcvt-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_fcvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
변환할 숫자입니다.

*count*<br/>
소수점 뒤의 자릿수입니다.

*dec*<br/>
저장된 소수점 위치의 포인터입니다.

*sign*<br/>
저장된 부호 표시기의 포인터입니다.

## <a name="return-value"></a>반환 값

**_fcvt** 숫자의 문자열 오류 발생 시 NULL에 대 한 포인터를 반환 합니다.

## <a name="remarks"></a>설명

**_fcvt** 함수는 null로 끝나는 문자열에 부동 소수점 숫자로 변환 합니다. *값* 매개 변수는 부동 소수점 숫자 변환입니다. **_fcvt** 의 숫자를 저장 *값* 문자열 및 null 문자 ('\0')를 추가 합니다. *count* 매개 변수는 자릿수는 소수점 뒤에 저장할 수를 지정 합니다. 초과 자릿수는 반올림 *count* 배치 합니다. 보다 적은 경우 *count* 0으로 채워서 자리의 전체 자릿수는 문자열입니다.

반환 된 전체 자릿수 **_fcvt** 초과 하지 것입니다 **_CVTBUFSIZE**합니다.

숫자만 문자열에 저장됩니다. 부호 및 소수점의 위치 *값* 에서 가져올 수 *dec* 호출 후 로그인 합니다. *dec* 매개 변수는 정수 값; 가리키는 정수 값이 문자열의 시작 부분에 대해 소수점의 위치를 제공 합니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. 매개 변수 *기호* 의 부호를 나타내는 정수를 가리키는 *값*합니다. 정수를 반환 하는 경우 0으로 설정 되어 *값* 가 양수이 고 0이 아닌 숫자 있으면으로 설정 되 *값* 음수입니다.

차이 **_ecvt** 및 **_fcvt** 의 해석에는 *count* 매개 변수입니다. **_ecvt** 해석 *count* 출력 문자열에 있는 숫자의 총 수로 반면 **_fcvt** 해석 *count* 뒤에 자릿수의 숫자는 소수점 합니다.

**_ecvt** 및 **_fcvt** 변환에 대해 단일 정적으로 할당 된 버퍼를 사용 합니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *dec* 또는 *기호* 가 null 인 경우 또는 *count* 가 0 이면에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 및 NULL이 반환 됩니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
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

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
