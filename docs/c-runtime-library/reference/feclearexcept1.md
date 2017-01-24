---
title: "feclearexcept | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feclearexcept"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feclearexcept"
  - "fenv/feclearexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "feclearexcept 함수"
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# feclearexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수로 지정 된 부동 소수점 예외 플래그를 제거 하려고 시도 합니다.  
  
## 구문  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### 매개 변수  
 `excepts`  
 선택을 취소 하는 예외 상태 플래그입니다.  
  
## 반환 값  
 경우에는 0을 반환 `excepts` 값이 0이 아니면 지정된 된 모든 예외를 지운 성공적으로 합니다. 0이 아닌 값을 반환합니다.  
  
## 설명  
 `feclearexcept` 부동의 선택을 취소 하려고 하는 함수에 지정 된 예외 상태 플래그 가리킨 `excepts`합니다. 함수는 fenv.h에 정의 된 이러한 예외 매크로 지원 합니다.  
  
|예외 매크로|설명|  
|------------|--------|  
|FE\_DIVBYZERO|이전 부동 소수점 연산에서; 특이성 또는 극 오류가 발생 했습니다. 무한대 값을 만들었습니다.|  
|FE\_INEXACT|이전 부동 소수점 작업의 저장된 된 결과 반올림 하는 함수 강제로 되었습니다.|  
|FE\_INVALID|이전 부동 소수점 연산에서 도메인 오류가 발생 했습니다.|  
|FE\_OVERFLOW|범위 오류가 발생 했습니다. 이전 부동 소수점 작업 결과를 표현할 너무 큽니다.|  
|FE\_UNDERFLOW|이전 부동 소수점 작업 결과 너무 작아 정밀; 표현할 수 denormal 값을 만들었습니다.|  
|FE\_ALLEXCEPT|모든 비트 OR 부동 소수점 예외를 지원 합니다.|  
  
 `excepts` 인수는 0 또는 하나 이상의 지원 되는 예외 매크로의 비트 OR 될 수 있습니다. 다른 인수 값의 결과가 정의 되지 않습니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`feclearexcept`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)