---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7154f6de192ee6b681ed0419126f3d4b682abb8c
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451347"
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc

RTC(런타임 오류 검사) 형식에 대한 간단한 설명을 반환합니다.

## <a name="syntax"></a>구문

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>매개 변수

*errnum*<br/>
0과 **_RTC_NumErrors**에서 반환한 값에서 1을 뺀 수 사이의 숫자입니다.

## <a name="return-value"></a>반환 값

런타임 오류 검사 시스템에서 검색된 오류 형식 중 하나에 대한 간단한 설명을 포함하는 문자열입니다. 오류는 작거나 0 보다 또는 보다 큰 값을 반환 하는 경우 [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** 반환 **NULL**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)<br/>
