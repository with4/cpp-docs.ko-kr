---
title: "fetestexcept | Microsoft Docs"
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
  - "fetestexcept"
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
  - "fetestexcept"
  - "fenv/fetestexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fetestexept 함수"
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fetestexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 설정 되어 있는 지정 된 부동 소수점 예외 상태 플래그 중 어떤 것을 결정 합니다.  
  
## 구문  
  
```  
int fetestexcept(  
   int excepts  
);  
  
```  
  
#### 매개 변수  
 `excepts`  
 부동 소수점 상태 플래그의 비트 OR 연산을을 테스트 합니다.  
  
## 반환 값  
 성공, 현재 예외 상태 플래그에 해당 하는 부동 소수점 예외 매크로의 비트 OR 연산자를 포함 하는 비트 마스크 반환 설정 합니다. 예외가 없는 경우 0을 반환 합니다 설정 됩니다.  
  
## 설명  
 부동에서 예외 발생 된 알아보려면 fetestexcept 함수를 사용 하 여 소수점 작업 합니다. 사용 하 여 `excepts` 매개 변수를 테스트 하는 예외 상태 플래그를 지정 합니다.`fetestexcept` 함수 \< fenv.h \>에 정의 된 이러한 예외 매크로 사용 하 여 `excepts` 및 반환 값:  
  
|예외 매크로|설명|  
|------------|--------|  
|FE\_DIVBYZERO|이전 부동 소수점 연산에서; 특이성 또는 극 오류가 발생 했습니다. 무한대 값을 만들었습니다.|  
|FE\_INEXACT|이전 부동 소수점 작업의 저장된 된 결과 반올림 하는 함수 강제로 되었습니다.|  
|FE\_INVALID|이전 부동 소수점 연산에서 도메인 오류가 발생 했습니다.|  
|FE\_OVERFLOW|범위 오류가 발생 했습니다. 이전 부동 소수점 작업 결과를 표현할 너무 큽니다.|  
|FE\_UNDERFLOW|이전 부동 소수점 작업 결과 너무 작아 정밀; 표현할 수 denormal 값을 만들었습니다.|  
|FE\_ALLEXCEPT|모든 비트 OR 부동 소수점 예외를 지원 합니다.|  
  
 지정 된 `excepts` 인수는 지원 되는 부동 소수점 예외 매크로 또는 비트 또는 두 개 이상의 매크로 중 하나는 0이 될 수 있습니다. 다른 모든 효과 `excepts` 인수 값이 정의 되지 않습니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하는 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fetestexcept`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feraiseexcept](../../c-runtime-library/reference/feraiseexcept.md)