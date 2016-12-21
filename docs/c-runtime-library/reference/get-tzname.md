---
title: "_get_tzname | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_tzname"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_get_tzname"
  - "get_tzname"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_tzname 함수"
  - "get_tzname 함수"
  - "시간대"
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_tzname
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간대 이름 또는 일광 절약 시간제 표준 시간 영역 이름 \(DST\) 의 문자 문자열 표현을 검색합니다.  
  
## 구문  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### 매개 변수  
 \[out\] `pReturnValue`  
 NULL 종결자를 포함한 `timeZoneName` 의 문자열 길이.  
  
 \[out\] `timeZoneName`  
 `index` 에 따라 시간대 이름 또는 일광 절약 시간제 표준 시간 영역 이름 \(DST\) 의 표현에 대한 문자 문자열의 주소.  
  
 \[in\] `sizeInBytes`  
 `timeZoneName` 문자 문자열의 크기\(바이트\)입니다.  
  
 \[in\] `index`  
 검색할 두 시간대 이름 중 하나의 인덱스.  
  
## 반환 값  
 성공적이면 0, 그렇지 않은 경우 `errno` 형식 값.  
  
 `timeZoneName` 가 `NULL` 이거나, 또는 `sizeInBytes` 0 이거나 0 보다 작은 경우\(둘 다는 아님\), [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 처럼 잘못된 매개 변수 처리기가 적용됩니다.  계속해서 실행하도록 허용된 경우, 함수는 `errno` 를 `EINVAL` 에 설정하고 `EINVAL`을 반환합니다.  
  
### 오류 조건  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|반환 값|`timeZoneName`의 내용입니다.|  
|--------------------|--------------------|-------------------|-------------|----------|----------------------------|  
|TZ 이름의 크기|`NULL`|0|0 또는 1|0|수정 안 됨|  
|TZ 이름의 크기|any|\> 0|0 또는 1|0|TZ 이름|  
|수정 안 됨|`NULL`|\> 0|any|`EINVAL`|수정 안 됨|  
|수정 안 됨|any|0|any|`EINVAL`|수정 안 됨|  
|수정 안 됨|any|\> 0|\> 1|`EINVAL`|수정 안 됨|  
  
## 설명  
 `_get_tzname` 함수는 `pReturnValue` 에서의 문자열의 크기와 함게 인덱스 값에 따라 `timeZoneName` 의 주소에 표준 시간대 이름 또는 일광 절약 시간제 표준 시간 영역 이름 \(DST\) 의 문자 문자열 표현을 검색합니다.  `timeZoneName` 이 `NULL` 이고 `sizeInBytes` 이 0 일 경우, 두 시간대의 문자열의 크기\(바이트\)는 `pReturnValue` 로 반환됩니다.  인덱스 값은 표준 시간대일 경우 0 이고 일광 절약 표준 시간대일 경우 1 이어야 합니다. 다른 인덱스 값은 정의 되지 않은 결과를 가집니다.  
  
### 인덱스 값  
  
|`index`|`timeZoneName`의 내용입니다.|`timeZoneName` 기본값|  
|-------------|----------------------------|------------------------|  
|0|표준 시간대 이름|"PST"|  
|1|일광 절약 표준 시간대 이름|"PDT"|  
|\> 1 또는 \< 0|`errno` 을 `EINVAL` 로 설정|수정 안 됨|  
  
 런타임 동안 값이 명시적으로 변경되지 않는한 기본값은 각각 "PST" 및 "PDT" 입니다.  이러한 문자 배열의 크기는 `TZNAME_MAX` 값에 따라 관리 됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_tzname`|\<time.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME\_MAX](../../c-runtime-library/tzname-max.md)