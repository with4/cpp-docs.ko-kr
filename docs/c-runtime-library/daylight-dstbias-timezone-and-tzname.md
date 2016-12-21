---
title: "_daylight, _dstbias, _timezone 및 _tzname | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tzname"
  - "_timezone"
  - "timezone"
  - "_daylight"
  - "_tzname"
  - "daylight"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "시간대"
  - "시간 조정"
  - "timezone 변수"
  - "_tzname 함수"
  - "_daylight 함수"
  - "_timezone 함수"
  - "daylight 함수"
  - "현지 시간 조정"
  - "timezone 함수"
  - "tzname 함수"
  - "시간대 변수"
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _daylight, _dstbias, _timezone 및 _tzname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`_daylight`, `_dstbias`, `_timezone` 와 `_tzname` 는 현지 시간 조정을 위한 시간과 날짜 루틴에서 사용됩니다.  이러한 전역 변수는 전역 변수 대신에 사용 될 수 있는 보안 기능이 강화된 버전의 함수에서는 종료됩니다.  
  
|전역 변수입니다.|기능적인 동일성.|  
|---------------|---------------|  
|`_daylight`|[\_get\_daylight](../c-runtime-library/reference/get-daylight.md)|  
|`_dstbias`|[\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)|  
|`_timezone`|[\_get\_timezone](../c-runtime-library/reference/get-timezone.md)|  
|`_tzname`|[\_get\_tzname](../c-runtime-library/reference/get-tzname.md)|  
  
 Time.h에서 선언된 것은 다음과 같습니다.  
  
## 구문  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## 설명  
 `_ftime` , `localtime`, 또는 `_tzset`의 호출에서, `_daylight`, `_dstbias`, `_timezone`, 그리고 `_tzname` 의 값은 `TZ` 환경 변수의 값으로부터 결정됩니다.  만일 명시적으로 `TZ`의 값을 설정하는 경우, `_tzname[0]` 과 `_tzname[1]` 은 각각 "PDT"와 "PST"의 기본설정을 포함합니다.  시간\-조작 기능들 \([\_tzset](../c-runtime-library/reference/tzset.md), [\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md), 그리고 [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)\)는 각가의 변수의 기본값에 대한 운영체제를 쿼리함으로써 `_daylight`, `_dstbias` 그리고 `_timezone` 의 값을 설정하도록 시도합니다.  시간 영역 전역 변수 값은 다음 표와 같습니다.  
  
|변수|값|  
|--------|-------|  
|`_daylight`|일광 절약 시간제 영역\(DST\)은 `TZ` 에서 지정되거나 운영체제로부터 결정되지 않습니다; 그렇지 않으면, 0입니다.  기본값은 1입니다.|  
|`_dstbias`|일광 절약 시간에 대한 오프셋.|  
|`_timezone`|초에서 다른점은 현지 시간과 협정 세계시간의 차이입니다.  기본값은 28,800입니다.|  
|`_tzname[0]`|시간 영역 이름은 `TZ` 환경변수로부터 파생됩니다.  기본값은 "PST"입니다.|  
|`_tzname[1]`|DST 영역 이름은 `TZ` 환경변수로부터 파생됩니다.  기본값은 "PDT"입니다.\(태평양 일광 절약 시간\)|  
  
## 참고 항목  
 [전역 변수](../c-runtime-library/global-variables.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)