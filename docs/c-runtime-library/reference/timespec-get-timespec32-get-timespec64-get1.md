---
title: timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 681f9d125a7f45dae2a8e604df655facdd246067
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get
첫 번째 인수를 통해 지정된 간격을 지정된 기본 시간을 기준으로 현재 일정 시간으로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
#### <a name="parameters"></a>매개 변수  
 `time_spec`  
 epoch 시작 이후 지난 시간(초 및 나노초)으로 설정된 구조체 포인터입니다.  
  
 `base`  
 기본 시간을 지정하는 0이 아닌 구현 특정 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `base` 값이고, 그렇지 않으면 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `timespec_get` 함수는 `time_spec` 인수를 통해 지정된 구조체의 현재 시간을 설정합니다. 이 구조체의 모든 버전에는 `tv_sec` 및 `tv_nsec`멤버가 있습니다. `tv_sec` 값은 `tv_nsec` 를 통해 지정된 epoch 시작 이후 지난 실수 초로 설정되고 `base`는 정수 나노초로 설정되며 시스템 클록의 해상도로 반올림됩니다.  
  
 **Microsoft 전용**  
  
 이들 함수는 `TIME_UTC` 만 `base` 값으로 지원합니다. `time_spec` 값은 epoch 시작, 1970년 1월 1일 자정, UTC(협정 세계시) 이후 지난 시간(초 및 나노초)으로 설정됩니다. `struct _timespec32`에서 `tv_sec` 는 `__time32_t` 값입니다. `struct _timespec64`에서 `tv_sec` 는 `__time64_t` 값입니다. `struct timespec`에서 `tv_sec` 는 `time_t` 형식으로, 전처리기 매크로 _USE_32BIT_TIME_T가 정의되었는지에 따라 32비트 또는 64비트 길이입니다. `timespec_get` 함수는 _USE_32BIT_TIME_T가 정의된 경우 `_timespec32_get` 를 호출하는 인라인 함수이고, 이외에는 `_timespec64_get`를 호출합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`timespec_get`에서 `_timespec32_get`에서 `_timespec64_get`|C: \<time.h>, C++: \<ctime> 또는 \<time.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)