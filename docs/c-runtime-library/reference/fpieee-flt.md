---
title: _fpieee_flt | Microsoft 문서
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fpieee_flt
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpieee_flt
- _fpieee_flt
dev_langs:
- C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 412eef6e3999c18901792643fa7a57ce18d19520
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403367"
---
# <a name="fpieeeflt"></a>_fpieee_flt

IEEE 부동 소수점 예외에 대한 사용자 정의 트랩 처리기를 호출합니다.

## <a name="syntax"></a>구문

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>매개 변수

*excCode*<br/>
예외 코드입니다.

*excInfo*<br/>
Windows NT 예외 정보 구조체에 대한 포인터입니다.

*처리기*<br/>
사용자의 IEEE 트랩 처리기 루틴에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

반환 값 **_fpieee_flt** 에서 반환한 값은 *처리기*합니다. 따라서 IEEE 필터 루틴은 SEH(구조적 예외 처리) 메커니즘의 예외 절에서 사용될 수 있습니다.

## <a name="remarks"></a>설명

**_fpieee_flt** 함수는 IEEE 부동 소수점 예외에 대 한 사용자 정의 트랩 처리기를 호출 하 고 모든 관련 정보를 제공 합니다. 이 루틴은 필요할 때 자신의 IEEE 예외 처리기를 호출하는 SEH 메커니즘에서 예외 필터로 사용됩니다.

**_FPIEEE_RECORD** , Fpieee.h에 정의 된 구조는 IEEE 부동 소수점 예외에 대 한 정보를 포함 합니다. 이 구조에서 사용자 정의 트랩 처리기에 전달 된 **_fpieee_flt**합니다.

|_FPIEEE_RECORD 필드|설명|
|----------------------------|-----------------|
|**RoundingMode**<br/>**전체 자릿수**|이러한 **서명 되지 않은** **int** 필드 정보가 부동 소수점 환경에 대 한 시간에는 예외가 발생 했습니다.|
|**작업**|이 **서명 되지 않은** **int** 필드 트랩을 발생 시킨 작업 형식을 나타냅니다. 형식이 비교 (**_FpCodeCompare**), 특수 중 하나를 제공할 수 있습니다 **_FPIEEE_COMPARE_RESULT** 값 (Fpieee.h에 정의 됨)에 **Result.Value** 필드입니다. 변환 유형 (**_FpCodeConvert**) 부동 소수점 변환 작업을 하는 동안 트랩이 발생 했음을 나타냅니다. 볼 수 있습니다는 **Operand1** 및 **결과** 시도 되는 변환 종류를 확인 하는 형식입니다.|
|**operand1**<br/>**operand2**<br/>**결과**|이러한 **_FPIEEE_VALUE** 구조체 형식 및 제안 된 결과 및 피연산자의 값을 나타냅니다. 각 구조에는 이러한 필드가 포함 됩니다.<br /><br /> **OperandValid** -응답 값이 유효한 지를 나타내는 플래그입니다.<br />**형식** -해당 값의 데이터 형식입니다. 해당 값이 잘못되어도 형식 유형이 반환될 수 있습니다.<br />**값** -결과 또는 피연산자 데이터 값입니다.|
|**원인**<br/>**사용**<br/>**Status**|**_FPIEEE_EXCEPTION_FLAGS** 부동 소수점 예외 형식당 1 비트 필드를 포함 합니다. 이러한 필드와 [_controlfp](control87-controlfp-control87-2.md)에 제공된 예외를 마스크하는 데 사용하는 인수 간에 대응 관계가 있습니다. 각 비트의 정확한 의미는 컨텍스트에 따라 달라집니다.<br /><br /> **원인** -각 설정 비트는 특정 발생 한 예외를 나타냅니다.<br />**사용 하도록 설정** -각 설정 비트는 특정 예외가 현재 마스크 임을 나타냅니다.<br />**상태** -각 설정 비트는 특정 예외가 현재 보류 중임을 나타냅니다. 여기에 의해 마스크 되었기 때문에 발생 하지 못한 예외 **_controlfp**합니다.|

사용할 수 없는 보류 중 예외는 해당 예외를 사용할 때 발생합니다. 사용 하는 경우이 정의 되지 않은 동작이 발생할 수 있습니다 **_fpieee_flt** 예외 필터로 합니다. 부동 소수점 예외를 사용하도록 설정하기 전에 항상 [_clearfp](clear87-clearfp.md)를 호출합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fpieee.c
// This program demonstrates the implementation of
// a user-defined floating-point exception handler using the
// _fpieee_flt function.

#include <fpieee.h>
#include <excpt.h>
#include <float.h>
#include <stddef.h>

int fpieee_handler( _FPIEEE_RECORD * );

int fpieee_handler( _FPIEEE_RECORD *pieee )
{
   // user-defined ieee trap handler routine:
   // there is one handler for all
   // IEEE exceptions

   // Assume the user wants all invalid
   // operations to return 0.

   if ((pieee->Cause.InvalidOperation) &&
       (pieee->Result.Format == _FpFormatFp32))
   {
        pieee->Result.Value.Fp32Value = 0.0F;

        return EXCEPTION_CONTINUE_EXECUTION;
   }
   else
      return EXCEPTION_EXECUTE_HANDLER;
}

#define _EXC_MASK    \
    _EM_UNDERFLOW  + \
    _EM_OVERFLOW   + \
    _EM_ZERODIVIDE + \
    _EM_INEXACT

int main( void )
{
   // ...

   __try {
      // unmask invalid operation exception
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);

      // code that may generate
      // fp exceptions goes here
   }
   __except ( _fpieee_flt( GetExceptionCode(),
                GetExceptionInformation(),
                fpieee_handler ) ){

      // code that gets control

      // if fpieee_handler returns
      // EXCEPTION_EXECUTE_HANDLER goes here

   }

   // ...
}
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
