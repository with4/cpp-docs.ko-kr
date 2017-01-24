---
title: "_RTC_SetErrorType | Microsoft Docs"
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
  - "_RTC_SetErrorType"
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
  - "RTC_SetErrorType"
  - "_RTC_SetErrorType"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "런타임 오류"
  - "RTC_SetErrorType 함수"
  - "_RTC_SetErrorType 함수"
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RTC\(런타임 오류 검사\)에서 발견된 오류를 형식에 연결합니다. 오류 처리기는 지정된 형식의 오류를 출력하는 방법을 처리합니다.  
  
## 구문  
  
```  
  
int _RTC_SetErrorType(  
   _RTC_ErrorNumber  
errnum  
,  
   int  
ErrType   
);  
  
```  
  
#### 매개 변수  
 *errnum*  
 0과 [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)에서 반환한 값에서 1을 뺀 수 사이의 숫자를 반환합니다.  
  
 *ErrType*  
 이 *errnum*에 할당할 값입니다. 예를 들어 **\_CRT\_ERROR**를 사용할 수 있습니다.`_CrtDbgReport`를 오류 처리기로 사용 중인 경우 *ErrType*은 [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)에서 정의된 기호 중 하나일 수만 있습니다. 사용자 고유의 오류 처리기\([\_RTC\_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)\)가 있는 경우 *errnum* 개수만큼 *ErrType*을 사용할 수 있습니다.  
  
 *ErrType* \_RTC\_ERRTYPE\_IGNORE에는 `_CrtSetReportMode`에 대한 특별한 의미가 있습니다. 오류가 무시됩니다.  
  
## 반환 값  
 오류 유형 `type`의 이전 값입니다.  
  
## 설명  
 기본적으로 모든 오류가 **\_CRT\_ERROR**에 해당하는 *ErrType* \= 1로 설정됩니다.**\_CRT\_ERROR**와 같은 기본 오류 유형에 대한 자세한 내용은 [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)를 참조하세요.  
  
 이 함수를 호출하려면 먼저 런타임 오류 검사 초기화 함수 중 하나를 호출해야 합니다. [C 런타임 라이브러리 없이 런타임 검사 사용](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_RTC_SetErrorType`|\<rtcapi.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)