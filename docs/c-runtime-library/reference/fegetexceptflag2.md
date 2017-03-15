---
title: "fegetexceptflag2 | Microsoft Docs"
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
  - "fegetexceptflag"
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
  - "fegetexceptflag"
  - "fenv/fegetexceptflag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fegetexceptflag 함수"
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fegetexceptflag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 예외를 지정 된 플래그의 현재 상태를 저장합니다.  
  
## 구문  
  
```  
int fegetexceptflag(   
   fexcept_t* pstatus,   
   int excepts   
);  
  
```  
  
#### 매개 변수  
 `pstatus`  
 에 대 한 포인터는 `fexcept_t` 로 지정 된 예외 플래그의 현재 값을 포함 하는 개체 `excepts`합니다.  
  
 `excepts`  
 에 저장 하는 부동 소수점 예외 플래그 `pstatus`합니다.  
  
## 반환 값  
 성공 시 0을 반환합니다. 0이 아닌 값을 반환합니다.  
  
## 설명  
 `fegetexceptflag` 로 지정 된 부동 소수점 예외 상태 플래그의 현재 상태를 저장 하는 함수 `excepts` 에 `fexcept_t` 가리키는 개체 `pstatus`합니다.`pstatus` 유효한 가리켜야 `fexcept_t` 개체 또는 후속 동작이 정의 되지 않습니다.`fegetexceptflag` 함수 \< fenv.h \>에 정의 된 이러한 예외 매크로 지원 합니다.  
  
|예외 매크로|설명|  
|------------|--------|  
|FE\_DIVBYZERO|이전 부동 소수점 연산에서; 특이성 또는 극 오류가 발생 했습니다. 무한대 값을 만들었습니다.|  
|FE\_INEXACT|이전 부동 소수점 작업의 저장된 된 결과 반올림 하는 함수 강제로 되었습니다.|  
|FE\_INVALID|이전 부동 소수점 연산에서 도메인 오류가 발생 했습니다.|  
|FE\_OVERFLOW|범위 오류가 발생 했습니다. 이전 부동 소수점 작업 결과를 표현할 너무 큽니다.|  
|FE\_UNDERFLOW|이전 부동 소수점 작업 결과 너무 작아 정밀; 표현할 수 denormal 값을 만들었습니다.|  
|FE\_ALLEXCEPT|모든 비트 OR 부동 소수점 예외를 지원 합니다.|  
  
 `excepts` 인수에 0이 될 수 있습니다 또는 매크로 중 두 개 이상의 지원 되는 부동 소수점 예외 매크로 또는 비트의 하나입니다. 다른 인수 값의 효과 정의 되지 않습니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하 여 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fegetexceptflag`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)