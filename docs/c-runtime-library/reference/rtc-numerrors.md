---
title: "_RTC_NumErrors | Microsoft Docs"
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
  - "_RTC_NumErrors"
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
  - "_RTC_NumErrors"
  - "RTC_NumErrors"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "런타임 오류"
  - "_RTC_NumErrors 함수"
  - "RTC_NumErrors 함수"
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_NumErrors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RTC\(런타임 오류 검사\)에서 검색될 수 있는 오류의 총 수를 반환합니다. 이 숫자를 **for** 루프의 컨트롤로 사용할 수 있습니다. 루프의 각 값은 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)에 전달됩니다.  
  
## 구문  
  
```  
  
int _RTC_NumErrors( void );  
  
```  
  
## 반환 값  
 오류의 총 수를 나타내는 값인 정수는 Visual C\+\+ 런타임 오류 검사를 통해 검색할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_RTC_NumErrors`|\<rtcapi.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)