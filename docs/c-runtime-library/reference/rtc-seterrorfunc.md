---
title: "_RTC_SetErrorFunc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_SetErrorFunc"
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
  - "RTC_SetErrorFunc"
  - "_RTC_SetErrorFunc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RTC_SetErrorFunc 함수"
  - "_RTC_SetErrorFunc 함수"
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _RTC_SetErrorFunc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RTC\(런타임 오류 검사\) 보고를 위한 처리기로 함수를 지정합니다. 이 함수는 사용되지 않습니다. 대신 `_RTC_SetErrorFuncW`를 사용하십시오.  
  
## 구문  
  
```  
  
_RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn  
 function   
);  
  
```  
  
#### 매개 변수  
 *함수*  
 런타임 오류 검사를 처리할 함수의 주소입니다.  
  
## 반환 값  
 이전에 정의된 오류 함수입니다. 이전에 정의된 함수가 없는 경우 NULL을 반환합니다.  
  
## 설명  
 이 함수를 사용하지 말고 `_RTC_SetErrorFuncW`를 대신 사용하세요. 이전 버전과의 호환성을 위해서만 유지됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)