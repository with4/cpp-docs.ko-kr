---
title: _ecvt_s | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 623d12bb515794a1d57b5a18e0e93e70d50a6812
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ecvts"></a>_ecvt_s

변환 된 **double** 숫자를 문자열로 합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_ecvt](ecvt.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _ecvt_s(
   char * _Buffer,
   size_t _SizeInBytes,
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
);
template <size_t size>
errno_t _ecvt_s(
   char (&_Buffer)[size],
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
); // C++ only
```

### <a name="parameters"></a>매개 변수

*_Buffer*<br/>
변환의 결과인 숫자 문자열에 대한 포인터로 채워집니다.

*_SizeInBytes*<br/>
버퍼의 크기(바이트)입니다.

*_Value*<br/>
변환할 숫자입니다.

*_Count*<br/>
저장된 자릿수입니다.

*_Dec*<br/>
저장된 소수점 위치입니다.

*_Sign*<br/>
변환된 숫자의 부호입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

다음 표에 나와 있는 잘못된 매개 변수의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **EINVAL**합니다.

### <a name="error-conditions"></a>오류 조건

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|반환 값|값을 *버퍼*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|모두|모두|모두|모두|모두|**EINVAL**|수정되지 않습니다.|
|하지 **NULL** (올바른 메모리를 가리킴)|<=0|모두|모두|모두|모두|**EINVAL**|수정되지 않습니다.|
|모두|모두|모두|모두|**NULL**|모두|**EINVAL**|수정되지 않습니다.|
|모두|모두|모두|모두|모두|**NULL**|**EINVAL**|수정되지 않습니다.|

## <a name="security-issues"></a>보안 문제

**_ecvt_s** 경우 액세스 위반이 발생 수 *버퍼* 올바른 메모리를 가리키지 않습니다 아니며 **NULL**합니다.

## <a name="remarks"></a>설명

**_ecvt_s** 함수는 부동 소수점 숫자 문자 문자열로 변환 합니다. *_Value* 매개 변수는 부동 소수점 숫자 변환입니다. 이 함수는 최대 저장 *count* 의 자리 *_Value* 문자열로 null 문자 ('\0')를 추가 하 고 있습니다. 경우에 자릿수 *_Value* 초과 *_Count*, 하위 자리에서 반올림 됩니다. 보다 적은 경우 *count* 숫자, 문자열에 0이 채워집니다.

숫자만 문자열에 저장됩니다. 부호 및 소수점의 위치 *_Value* 에서 가져올 수 *_Dec* 및 *_Sign* 호출 후 합니다. *_Dec* 매개 변수는 문자열의 시작 부분에 대해 소수점의 위치를 제공 하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. *_Sign* 매개 변수 변환 된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.

버퍼 길이를 **_CVTBUFSIZE** 모든 부동 소수점 값에 적합 합니다.

차이 **_ecvt_s** 및 **_fcvt_s** 의 해석에는 *_Count* 매개 변수입니다. **_ecvt_s** 해석 *_Count* 출력 문자열에 있는 숫자의 총 수로 반면 **_fcvt_s** 해석 *_Count* 뒤에 자릿수의 숫자 소수점 합니다.

C++에서는 템플릿 오버로드로 인해 이 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|선택적 헤더|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// ecvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( )
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_ecvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 12000
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
