---
title: "_get_tzname | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_tzname
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
dev_langs: C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f70e928c3877bf5d660231cbe2646f6cf72575e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="gettzname"></a>_get_tzname
표준 시간대 이름 또는 일광 표준 시간대 이름(DST)의 문자열 표현을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `pReturnValue`  
 NULL 종결자를 포함한 `timeZoneName`의 문자열 길이입니다.  
  
 [out] `timeZoneName`  
 `index`에 따른 표준 시간대 이름 또는 일광 표준 시간대 이름(DST)의 표현에 대한 문자열 주소입니다.  
  
 [in] `sizeInBytes`  
 `timeZoneName` 문자열의 크기(바이트)입니다.  
  
 [in] `index`  
 검색할 두 표준 시간대 이름 중 하나의 인덱스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 0이고, 실패하면 `errno` 형식 값입니다.  
  
 `timeZoneName`이 `NULL`이거나 `sizeInBytes`가 0보다 작거나 같으면(한 조건에만 해당) [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|반환 값|`timeZoneName`의 내용|  
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|  
|TZ 이름의 크기|`NULL`|0|0 또는 1|0|수정 안 됨|  
|TZ 이름의 크기|any|> 0|0 또는 1|0|TZ 이름|  
|수정 안 됨|`NULL`|> 0|any|`EINVAL`|수정 안 됨|  
|수정 안 됨|any|0|any|`EINVAL`|수정 안 됨|  
|수정 안 됨|any|> 0|> 1|`EINVAL`|수정 안 됨|  
  
## <a name="remarks"></a>설명  
 `_get_tzname` 함수는 표준 시간대 이름 또는 일광 표준 시간대 이름(DST)의 문자열 표현을 인덱스 값에 따른 `timeZoneName`의 주소로 검색하고 `pReturnValue`에서 문자열 크기를 검색합니다. `timeZoneName`이 `NULL`이고 `sizeInBytes`가 0이면 한쪽 표준 시간대의 문자열 크기(바이트)만 `pReturnValue`에서 반환됩니다. 인덱스 값은 표준 시간대인 경우 0, 일광 표준 시간대인 경우 1입니다. 다른 모든 인덱스 값에는 결정되지 않은 결과가 포함됩니다.  
  
### <a name="index-values"></a>인덱스 값  
  
|`index`|`timeZoneName`의 내용|`timeZoneName` 기본값|  
|-------------|--------------------------------|----------------------------------|  
|0|표준 시간대 이름|"PST"|  
|1|일광 표준 시간대 이름|"PDT"|  
|> 1 또는 < 0|`EINVAL`로 설정된 `errno`|수정 안 됨|  
  
 런타임에 값을 명시적으로 변경하는 경우가 아니면 기본값은 각각 "PST" 및 "PDT"입니다.  이러한 문자 배열의 크기는 `TZNAME_MAX` 값으로 관리합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME_MAX](../../c-runtime-library/tzname-max.md)