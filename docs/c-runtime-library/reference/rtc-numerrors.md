---
title: _RTC_NumErrors | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2034dd9c1e255196c66c4385e68c51845915ff59
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="rtcnumerrors"></a>_RTC_NumErrors
RTC(런타임 오류 검사)에서 검색될 수 있는 오류의 총 수를 반환합니다. 이 숫자를 **for** 루프의 컨트롤로 사용할 수 있습니다. 루프의 각 값은 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)에 전달됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
int _RTC_NumErrors( void );  
  
```  
  
## <a name="return-value"></a>반환 값  
 오류의 총 수를 나타내는 값인 정수는 Visual C++ 런타임 오류 검사를 통해 검색할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_RTC_NumErrors`|\<rtcapi.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)