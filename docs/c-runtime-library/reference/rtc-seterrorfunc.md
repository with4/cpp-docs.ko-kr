---
title: _RTC_SetErrorFunc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_SetErrorFunc
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
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
dev_langs: C++
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fa6d2e05668eac7909cb7805c5843ee6584b941f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc
RTC(런타임 오류 검사) 보고를 위한 처리기로 함수를 지정합니다. 이 함수는 사용되지 않습니다. 대신 `_RTC_SetErrorFuncW` 를 사용하십시오.  
  
## <a name="syntax"></a>구문  
  
```  
  
      _RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn function   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *function*  
 런타임 오류 검사를 처리할 함수의 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 이전에 정의된 오류 함수입니다. 이전에 정의된 함수가 없는 경우 NULL을 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 함수를 사용하지 말고 `_RTC_SetErrorFuncW`를 대신 사용하세요. 이전 버전과의 호환성을 위해서만 유지됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)