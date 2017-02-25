---
title: "feholdexcept2 | Microsoft Docs"
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
  - "feholdexcept"
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
  - "feholdexcept"
  - "fenv/feholdexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feholdexcept 함수"
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# feholdexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 부동 소수점 환경에에서 저장 지정된 된 개체, 부동 소수점 상태 플래그를 지우고 하 고, 가능한 경우 중단 없이 모드로 부동 소수점 환경을 넣습니다.  
  
## 구문  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
  
```  
  
#### 매개 변수  
 `penv`  
 에 대 한 포인터는 `fenv_t` 부동 소수점 환경 복사본을 포함 하는 개체입니다.  
  
## 반환 값  
 경우에 함수를 성공적으로 중단 하지 않고 부동 소수점 예외 처리를 설정할 수는 0을 반환 합니다.  
  
## 설명  
 `feholdexcept` 함수를 사용 하는 현재 환경의 부동 지점에서 상태 저장는 `fenv_t` 가리키는 개체 `penv`, 부동 소수점 예외에서 실행을 중단 하도록 환경을 설정 하 고 있습니다. 이 중단 하지 않고 모드 라고 합니다.  이 모드를 사용 하 여 환경을 복원 될 때까지 계속 [fesetenv](../Topic/fesetenv2.md) 또는 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)합니다.  
  
 이 함수를 하나 이상의 부동 소수점 예외를 호출자에서 숨겨야 하는 서브루틴의 시작 부분에 사용할 수 있습니다. 예외를 보고 하려면 지울 수 있습니다 단순히 원치 않는 예외를 사용 하 여 [feclearexcept,](../../c-runtime-library/reference/feclearexcept1.md) 다음 호출을 사용 하 여 중단 하지 않고 모드를 종료 하 고 `feupdateenv`합니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하 여 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하세요.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`feholdexcept`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](../Topic/fesetenv2.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)