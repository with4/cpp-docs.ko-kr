---
title: "_get_daylight | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __daylight
- _get_daylight
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
- get_daylight
- _get_daylight
dev_langs:
- C++
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 441861208d699a056084970a3d60d629ba79dc77
ms.lasthandoff: 02/24/2017

---
# <a name="getdaylight"></a>_get_daylight
일광 절약 시간 오프셋(시간)을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      error_t _get_daylight(   
    int* hours  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hours`  
 일관 절약 시간의 오프셋(시간)입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면&0;이고 오류가 발생하면 `errno` 값입니다.  
  
## <a name="remarks"></a>설명  
 `_get_daylight` 함수는 일광 절약 시간의 시간 수를 정수로 검색합니다. 일광 절약 시간이 적용 중인 경우 몇몇 지역에서&2;시간 오프셋을 따르고 있더라도 기본 오프셋은&1;시간입니다.  
  
 `hours`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
 매크로 `_daylight` 또는 사용되지 않는 함수 `__daylight` 대신 이 함수를 사용하는 것이 좋습니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_get_daylight`|\<time.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
