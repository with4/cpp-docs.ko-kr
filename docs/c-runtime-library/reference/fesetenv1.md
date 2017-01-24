---
title: "fesetenv | Microsoft Docs"
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
  - "fesetenv"
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
  - "fesetenv"
  - "fenv/fesetenv"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fesetenv 함수"
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fesetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 부동 소수점 환경을 설정합니다.  
  
## 구문  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
  
```  
  
#### 매개 변수  
 `penv`  
 에 대 한 포인터는 `fenv_t` 를 호출 하 여 부동 소수점 환경 설정 포함 된 개체 [fegetenv](../Topic/fegetenv2.md) 또는 [feholdexcept](../Topic/feholdexcept1.md)합니다. FE\_DFL\_ENV 매크로 사용 하 여 기본 시작 부동 소수점 환경도 지정할 수 있습니다.  
  
## 반환 값  
 환경을 성공적으로 설정 된 경우 0을 반환 합니다. 0이 아닌 값을 반환합니다.  
  
## 설명  
 `fesetenv` 의 현재 부동 소수점 환경에 저장 된 값을 설정 하는 함수는 `fenv_t` 가리키는 개체 `penv`합니다. 부동 지점 환경은 집합 상태 플래그 및 부동 소수점 계산에 영향을 주는 모드를 제어 합니다. 반올림 모드 및 부동 소수점 예외에 대 한 상태 플래그가 포함 됩니다. 경우 `penv` FE\_DFL\_ENV 되었거나 유효한를 가리키지 않습니다 `fenv_t` 개체를 후속 동작이 정의 되지 않습니다.  
  
 이 함수를 호출 하는 예외에 있는 상태 플래그를 설정 된 `penv` 개체를 가져오지만 해당 하는 예외를 발생 하지 않습니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하는 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fesetenv`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)