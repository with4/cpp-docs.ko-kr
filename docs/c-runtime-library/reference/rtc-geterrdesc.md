---
title: "_RTC_GetErrDesc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_GetErrDesc"
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
apitype: "DLLExport"
f1_keywords: 
  - "RTC_GetErrDesc"
  - "_RTC_GetErrDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "런타임 오류"
  - "_RTC_GetErrDesc 함수"
  - "RTC_GetErrDesc 함수"
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _RTC_GetErrDesc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RTC\(런타임 오류 검사\) 형식에 대한 간단한 설명을 반환합니다.  
  
## 구문  
  
```  
  
const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber   
errnum  
);  
  
```  
  
#### 매개 변수  
 *errnum*  
 0과 `_RTC_NumErrors`에서 반환한 값에서 1을 뺀 수 사이의 숫자를 반환합니다.  
  
## 반환 값  
 런타임 오류 검사 시스템에서 검색된 오류 형식 중 하나에 대한 간단한 설명을 포함하는 문자열입니다. 오류가 0보다 작거나, [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)에서 반환된 값보다 크거나 같은 경우 `_RTC_GetErrDesc`는 NULL을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_RTC_GetErrDesc`|\<rtcapi.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)