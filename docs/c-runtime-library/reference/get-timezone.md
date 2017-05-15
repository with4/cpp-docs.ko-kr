---
title: "_get_timezone | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_timezone
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
- _get_timezone
- get_timezone
dev_langs:
- C++
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 7ddada62e9bb209d8b5ffad6af3728edce36e443
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="gettimezone"></a>_get_timezone
현지 시간과 UTC 사이의 차이(초)를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      error_t _get_timezone(   
    long* seconds  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `seconds`  
 UTC와 현지 시간 사이의 차이(초)입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 0이고 오류가 발생하면 `errno` 값입니다.  
  
## <a name="remarks"></a>설명  
 `_get_timezone` 함수는 UTC와 현지 시간 사이의 차이(초)를 정수로 검색합니다. 기본값은 태평양 표준시(UTC보다 8시간 뒤)에 대해 28,800초입니다.  
  
 `seconds`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_get_timezone`|\<time.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
