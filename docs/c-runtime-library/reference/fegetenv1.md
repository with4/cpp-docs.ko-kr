---
title: "fegetenv1 | Microsoft Docs"
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
  - "fetegenv"
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
  - "fegetenv"
  - "fenv/fegetenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fetegenv 함수"
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fegetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 개체에서 현재 부동 소수점 환경을 저장합니다.  
  
## 구문  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### 매개 변수  
 `penv`  
 에 대 한 포인터는 `fenv_t` 현재 부동 소수점 환경 값을 포함 하는 개체입니다.  
  
## 반환 값  
 부동 소수점 환경에 성공적으로 저장 된 경우 0 반환 `penv`합니다. 0이 아닌 값을 반환합니다.  
  
## 설명  
 `fegetenv` 함수에서 가리키는 개체의 현재 부동 소수점 환경 저장 `penv`합니다. 부동 지점 환경은 집합 상태 플래그 및 부동 소수점 계산에 영향을 주는 모드를 제어 합니다. 반올림 방향 모드 및 부동 소수점 예외에 대 한 상태 플래그가 포함 됩니다. 경우 `penv` 유효한를 가리키지 않습니다 `fenv_t` 개체를 후속 동작이 정의 되지 않습니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하는 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fegetenv`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)