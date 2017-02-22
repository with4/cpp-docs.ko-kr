---
title: "feraiseexcept | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feraiseexcept"
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
apitype: "HeaderDef"
f1_keywords: 
  - "feraiseexcept"
  - "fenv/feraiseexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feraiseexcept 함수"
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# feraiseexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 부동 소수점 예외를 발생 시킵니다.  
  
## 구문  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### 매개 변수  
 `excepts`  
 시키려면 부동 소수점 예외입니다.  
  
## 반환 값  
 지정 된 모든 예외를 성공적으로 발생 한 경우 0을 반환 합니다.  
  
## 설명  
 `feraiseexcept` 함수에 지정 된 부동 소수점 예외를 발생 하려고 `excepts`합니다.`feraiseexcept` 함수 \< fenv.h \>에 정의 된 이러한 예외 매크로 지원 합니다.  
  
|예외 매크로|설명|  
|------------|--------|  
|FE\_DIVBYZERO|이전 부동 소수점 연산에서; 특이성 또는 극 오류가 발생 했습니다. 무한대 값을 만들었습니다.|  
|FE\_INEXACT|이전 부동 소수점 작업의 저장된 된 결과 반올림 하는 함수 강제로 되었습니다.|  
|FE\_INVALID|이전 부동 소수점 연산에서 도메인 오류가 발생 했습니다.|  
|FE\_OVERFLOW|범위 오류가 발생 했습니다. 이전 부동 소수점 작업 결과를 표현할 너무 큽니다.|  
|FE\_UNDERFLOW|이전 부동 소수점 작업 결과 너무 작아 정밀; 표현할 수 denormal 값을 만들었습니다.|  
|FE\_ALLEXCEPT|모든 비트 OR 부동 소수점 예외를 지원 합니다.|  
  
 `excepts` 인수에 0이 될 수 있습니다 하나 또는 두 개 이상의 지원 되는 예외 매크로의 예외 매크로 값 또는 비트입니다. 지정 된 예외 매크로 중 하나 FE\_OVERFLOW 또는 FE\_UNDERFLOW 경우 부작용으로 FE\_INEXACT 예외가 발생할 수 있습니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하 여 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
 **Microsoft 전용:** 에 지정 된 예외 `excepts` FE\_INVALID 순서 대로 발생 FE\_DIVBYZERO FE\_OVERFLOW, FE\_UNDERFLOW, FE\_INEXACT 합니다. 그러나 FE\_INEXACT 발생할 수 있습니다 FE\_OVERFLOW 또는 FE\_UNDERFLOW 발생 하는 경우에 지정 되지 않은 경우에 `excepts`합니다.**Microsoft 전용 종료**  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`feraiseexcept`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)