---
title: "_RTC_SetErrorFuncW | Microsoft Docs"
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
  - "_RTC_SetErrorFuncW"
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
  - "_RTC_SetErrorFuncW"
  - "RTC_SetErrorFuncW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "런타임 오류"
  - "RTC_SetErrorFuncW 함수"
  - "_RTC_error_fnW 형식 정의"
  - "_RTC_SetErrorFuncW 함수"
  - "RTC_error_fnW 형식 정의"
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorFuncW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RTC\(런타임 오류 검사\) 보고를 위한 처리기로 함수를 지정합니다.  
  
## 구문  
  
```  
  
_RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW  
 function   
);  
  
```  
  
#### 매개 변수  
 `function`  
 런타임 오류 검사를 처리할 함수의 주소입니다.  
  
## 반환 값  
 이전에 정의된 오류 함수 또는 이전에 정의된 함수가 없는 경우 `NULL`입니다.  
  
## 설명  
 새 코드에서는 `_RTC_SetErrorFuncW`만 사용합니다.`_RTC_SetErrorFunc`는 이전 버전과의 호환성을 위해서만 라이브러리에 포함되었습니다.  
  
 `_RTC_SetErrorFuncW` 콜백은 연결된 구성 요소에만 적용되고 전체적으로 적용되지 않습니다.  
  
 `_RTC_SetErrorFuncW`에 전달하는 주소가 유효한 오류 처리 함수의 주소인지 확인합니다.  
  
 [\_RTC\_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)을 사용하여 오류에 \-1의 한 형식을 할당한 경우 오류 처리 함수가 호출되지 않습니다.  
  
 이 함수를 호출하려면 먼저 런타임 오류 검사 초기화 함수 중 하나를 호출해야 합니다. 자세한 내용은 [C 런타임 라이브러리 없이 런타임 검사 사용](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md)을 참조하십시오.  
  
 **\_RTC\_error\_fnW**는 다음과 같이 정의됩니다.  
  
 **typedef int \(\_\_cdecl \*\_RTC\_error\_fnW\)\(int**  `errorType` **, const wchar\_t \*** *filename* **, int**  *linenumber* **, const wchar\_t \*** `moduleName` **, const wchar\_t \*** *format* **, ...\);**  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `errorType`  
 [\_RTC\_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)으로 지정된 오류 유형입니다.  
  
 *filename*  
 오류가 발생한 원본 파일 또는 디버그 정보를 사용할 수 없는 경우 null입니다.  
  
 *linenumber*  
 오류가 발생한 *filename*의 줄 또는 디버그 정보를 사용할 수 없는 경우 0입니다.  
  
 `moduleName`  
 오류가 발생한 DLL 또는 실행 파일 이름입니다.  
  
 *format*  
 나머지 매개 변수를 사용하여 오류 메시지를 표시할 printf 스타일 문자열입니다. VA\_ARGLIST의 첫 번째 인수는 발생한 RTC 오류 번호입니다.  
  
 **\_RTC\_error\_fnW**를 사용하는 방법을 보여 주는 예제는 [네이티브 런타임 검사 사용자 지정](../Topic/Native%20Run-Time%20Checks%20Customization.md)을 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h\>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하세요.  
  
## 참고 항목  
 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)