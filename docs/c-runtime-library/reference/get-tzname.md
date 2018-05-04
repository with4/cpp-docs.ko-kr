---
title: _get_tzname | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_tzname
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 182bad39b461efc18b120875432d6ce07be2a884
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="gettzname"></a>_get_tzname

표준 시간대 이름 또는 일광 표준 시간대 이름(DST)의 문자열 표현을 검색합니다.

## <a name="syntax"></a>구문

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
문자열 길이 *표준 시간대 이름* NULL 종결자를 포함 합니다.

*표준 시간대 이름*<br/>
에 따라 표준 시간대 이름 또는 일광 표준시 영역 이름 (DST) 표현에 대 한 문자에 대 한 문자열의 주소 *인덱스*합니다.

*sizeInBytes*<br/>
크기는 *표준 시간대 이름* 문자열 (바이트)에서입니다.

*index*<br/>
검색할 두 표준 시간대 이름 중 하나의 인덱스입니다.

## <a name="return-value"></a>반환 값

성공 하면 0이 고, 그렇지는 **errno** 값을 입력 합니다.

어느 경우 *표준 시간대 이름* 은 **NULL**, 또는 *sizeInBytes* 가 0 이거나 0 (하나만), 보다 작은 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **EINVAL**합니다.

### <a name="error-conditions"></a>오류 조건

|*pReturnValue*|*표준 시간대 이름*|*sizeInBytes*|*index*|반환 값|내용을 *표준 시간대 이름*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ 이름의 크기|**NULL**|0|0 또는 1|0|수정 안 됨|
|TZ 이름의 크기|any|> 0|0 또는 1|0|TZ 이름|
|수정 안 됨|**NULL**|> 0|모두|**EINVAL**|수정 안 됨|
|수정 안 됨|모두|0|모두|**EINVAL**|수정 안 됨|
|수정 안 됨|모두|> 0|> 1|**EINVAL**|수정 안 됨|

## <a name="remarks"></a>설명

**_get_tzname** 함수 검색의 주소에 표준 시간대 이름 또는 일광 절약 시간 표준 영역 이름 (DST)의 문자 문자열 표현을 *표준 시간대 이름* 인덱스에 따라 값에서 문자열의 크기와 함께 *pReturnValue*합니다. 경우 *표준 시간대 이름* 은 **NULL** 및 *sizeInBytes* 0 인 바이트의 영역에 반환 된 두 시간 문자열 크기 *pReturnValue*. 인덱스 값은 표준 시간대인 경우 0, 일광 표준 시간대인 경우 1입니다. 다른 모든 인덱스 값에는 결정되지 않은 결과가 포함됩니다.

### <a name="index-values"></a>인덱스 값

|*index*|내용을 *표준 시간대 이름*|*표준 시간대 이름* 기본값|
|-------------|--------------------------------|----------------------------------|
|0|표준 시간대 이름|"PST"|
|1|일광 표준 시간대 이름|"PDT"|
|> 1 또는 < 0|**errno** 로 설정 **EINVAL**|수정 안 됨|

런타임에 값을 명시적으로 변경하는 경우가 아니면 기본값은 각각 "PST" 및 "PDT"입니다.  이러한 문자 배열 크기에 따라 관리 됩니다 **TZNAME_MAX** 값입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[TZNAME_MAX](../../c-runtime-library/tzname-max.md)<br/>
