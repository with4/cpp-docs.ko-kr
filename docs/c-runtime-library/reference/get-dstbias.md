---
title: "_get_dstbias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_dstbias"
  - "__dstbias"
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
  - "__dstbias"
  - "_get_dstbias"
  - "get_dstbias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__dstbias"
  - "_get_dstbias 함수"
  - "일광 절약 시간 오프셋"
  - "get_dstbias 함수"
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _get_dstbias
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일광 절약 시간 오프셋\(초\)을 검색합니다.  
  
## 구문  
  
```  
  
error_t _get_dstbias(      int* seconds );  
```  
  
#### 매개 변수  
 `seconds`  
 일관 절약 시간의 오프셋\(초\)입니다.  
  
## 반환 값  
 성공하면 0이고 오류가 발생하면 `errno` 값입니다.  
  
## 설명  
 `_get_dstbias` 함수는 일광 절약 시간의 초 수를 정수로 검색합니다.  일광 절약 시간이 적용 중인 경우 몇몇 지역에서 2시간 오프셋을 따르고 있더라도 기본 오프셋은 3,600초입니다. 이 값은 한 시간을 나타내는 초 수입니다.  
  
 `seconds`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
 매크로 `_dstbias` 또는 사용되지 않는 함수 `__dstbias` 대신 이 함수를 사용하는 것이 좋습니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_dstbias`|\<time.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)