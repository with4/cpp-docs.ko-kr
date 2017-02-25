---
title: "feupdateenv | Microsoft Docs"
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
  - "feupdateenv"
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
  - "feupdateenv"
  - "fenv/feupdateenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feupdateenv 함수"
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# feupdateenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 발생된 하는 부동 소수점 예외를 저장 하 고, 지정 된 부동 소수점 환경 상태를 복원 및 저장 된 부동 소수점 예외를 발생 시킵니다.  
  
## 구문  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
#### 매개 변수  
 `penv`  
 에 대 한 포인터는 `fenv_t` 를 호출 하 여 부동 소수점 환경 설정 포함 된 개체 [fegetenv](../Topic/fegetenv2.md) 또는 [feholdexcept](../Topic/feholdexcept1.md)합니다. FE\_DFL\_ENV 매크로 사용 하 여 기본 시작 부동 소수점 환경도 지정할 수 있습니다.  
  
## 반환 값  
 모든 작업이 성공적으로 완료 하는 경우 0을 반환 합니다. 0이 아닌 값을 반환합니다.  
  
## 설명  
 `feupdateenv` 함수는 여러 작업을 수행 합니다. 첫째, 자동 저장에는 현재 발생된 한 부동 소수점 예외 상태 플래그를 저장합니다. 그런 다음, 현재 부동 소수점 환경에 저장 된 값에서 설정 된 `fenv_t` 가리키는 개체 `penv`합니다. 경우 `penv` FE\_DFL\_ENV 되었거나 유효한를 가리키지 않습니다 `fenv_t` 개체를 후속 동작이 정의 되지 않습니다. 마지막으로, `feupdateenv` 로컬에 저장 된 부동 소수점 예외를 발생 시킵니다.  
  
 사용 하 여 액세스를 방지할 수 있는 부동 소수점 최적화를 해제 해야이 함수를 사용 하는 `#pragma fenv_access(on)` 호출 하기 전에 지시문입니다. 자세한 내용은 [fenv\_access](../../preprocessor/fenv-access.md)을 참조하십시오.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`feupdateenv`|\<fenv.h\>|\<cfenv\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)