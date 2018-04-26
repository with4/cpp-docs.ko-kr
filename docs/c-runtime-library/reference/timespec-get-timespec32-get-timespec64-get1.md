---
title: timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
dev_langs:
- C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04665cdc46f2bb5aa880eae6022629df1a6258bb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get

첫 번째 인수를 통해 지정된 간격을 지정된 기본 시간을 기준으로 현재 일정 시간으로 설정합니다.

## <a name="syntax"></a>구문

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);

```

### <a name="parameters"></a>매개 변수

*time_spec*<br/>
epoch 시작 이후 지난 시간(초 및 나노초)으로 설정된 구조체 포인터입니다.

*base*<br/>
기본 시간을 지정하는 0이 아닌 구현 특정 값입니다.

## <a name="return-value"></a>반환 값

값 *기본* 성공 하 고, 그렇지 않으면 0이 반환 됩니다.

## <a name="remarks"></a>설명

**timespec_get** 가 가리키는 구조체의 현재 시간을 설정 하는 함수는 *time_spec* 인수입니다. 이 구조체의 모든 버전에는 두 멤버는 **tv_sec** 및 **tv_nsec**합니다. **tv_sec** 실수 시간 (초) 값이 설정 및 **tv_nsec** 하기 위해 정수 나노초로 반올림 시스템 클록의 해상도로 로지정된epoch시작된이후*기본*합니다.

**Microsoft 전용**

이러한 함수는 지원만 **TIME_UTC** 로 *기본* 값입니다. 이 설정의 *time_spec* 값의 초 및 나노초는 epoch 시작, 1970 년 1 월 1 일 자정, Utc (협정 세계시) 이후 수 있습니다. 에 **구조체** **_timespec32**, **tv_sec** 는 **__time32_t** 값입니다. 에 **구조체** **_timespec64**, **tv_sec** 는 **__time64_t** 값입니다. 에 **구조체** **timespec**, **tv_sec** 는 **time_t** 32 비트 또는 64 비트 길이 인지 여부에 따라 형식을 전처리기 매크로 _USE_32BIT_TIME_T이 정의 합니다. **timespec_get** 함수를 호출 하는 인라인 함수는 **_timespec32_get** _USE_32BIT_TIME_T이 정의 하 고; 그렇지 않으면 호출 **_timespec64_get**합니다.

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<time.h>, C++: \<ctime> 또는 \<time.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
