---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 4850b9e6da16ad2b446b532281d65cd3bf535698
ms.lasthandoff: 02/24/2017

---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc
RTC(런타임 오류 검사) 형식에 대한 간단한 설명을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber errnum   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *errnum*  
 0과 `_RTC_NumErrors`에서 반환한 값에서&1;을 뺀 수 사이의 숫자를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 런타임 오류 검사 시스템에서 검색된 오류 형식 중 하나에 대한 간단한 설명을 포함하는 문자열입니다. 오류가&0;보다 작거나, [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)에서 반환된 값보다 크거나 같은 경우 `_RTC_GetErrDesc`는 NULL을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)
