---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb3b8e5f6fb602675538c6588372b87df8781ac
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW

RTC(런타임 오류 검사) 보고를 위한 처리기로 함수를 지정합니다.

## <a name="syntax"></a>구문

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>매개 변수

*function*<br/>
런타임 오류 검사를 처리할 함수의 주소입니다.

## <a name="return-value"></a>반환 값

이전에 정의 된 오류 독립적입니다. 또는 **NULL** 없는 이전에 정의 된 함수가 없는 경우.

## <a name="remarks"></a>설명

새 코드를 사용 하 여만 **_RTC_SetErrorFuncW**합니다. **_RTC_SetErrorFunc** 이전 버전과 호환성에 대 한 라이브러리에만 포함 되어 있습니다.

**_RTC_SetErrorFuncW** 콜백, 연결 된 구성 요소에만 적용 됩니다 하지만 전역으로 사용 되지 않습니다.

다음 사항을 확인 전달 하는 주소 **_RTC_SetErrorFuncW** 의 유효한 오류 처리 함수입니다.

경우 오류가 여 할당 된-1의 형식을 사용 하 여 [_RTC_SetErrorType](rtc-seterrortype.md), 오류 처리 함수가 호출 되지 않습니다.

이 함수를 호출하려면 먼저 런타임 오류 검사 초기화 함수 중 하나를 호출해야 합니다. 자세한 내용은 [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)을 참조하십시오.

**_RTC_error_fnW** 는 다음과 같이 정의됩니다.

> **typedef int (__cdecl \*_RTC_error_fnW) (int** *errorType* **, const wchar_t \***  *filename* **, int***linenumber* **, const wchar_t \***  *moduleName* **, const wchar_t \***  *형식* **,...);** 

다음은 각 문자에 대한 설명입니다.

*errorType* 변수로 지정 된 오류의 유형을 [_RTC_SetErrorType](rtc-seterrortype.md)합니다.

*filename* 오류가 발생 하는 소스 파일 또는 디버그 정보가 없는 경우 null입니다.

*linenumber* 함수의 줄 *filename* 오류가 발생 하거나 디버그 정보가 없는 경우 0입니다.

*moduleName* DLL 또는 실행 파일 이름이 오류가 발생 합니다.

*형식* 나머지 매개 변수를 사용 하 여 오류 메시지를 표시할 printf 스타일 문자열입니다. VA_ARGLIST의 첫 번째 인수는 발생한 RTC 오류 번호입니다.

**_RTC_error_fnW** 사용 방법을 보여 주는 예제는 [네이티브 런타임 검사 사용자 지정](/visualstudio/debugger/native-run-time-checks-customization)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)<br/>
