---
title: "신호 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SIGTERM"
  - "SIGFPE"
  - "SIGABRT"
  - "SIGILL"
  - "SIGINT"
  - "SIGSEGV"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIGABRT 상수"
  - "SIGFPE 상수"
  - "SIGILL 상수"
  - "SIGINT 상수"
  - "신호 상수"
  - "SIGSEGV 상수"
  - "SIGTERM 상수"
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 신호 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
#include <signal.h>  
```  
  
## 설명  
 `sig` 인수는 아래\(SIGNAL.H에서 정의된\) 기록된 매니페스트 상수들 중 하나여야 합니다.  
  
 `SIGABRT`  
 Abnormal termination.  기본 작업은 종료 코드 3을 사용하여 호출하는 프로그램을 종료합니다.  
  
 `SIGABRT_COMPAT`  
 SIGABRT과 동일합니다.  다른 플랫폼과 호환됩니다.  
  
 `SIGFPE`  
 잘못된 연산이나 0으로 나누기, 오버플로우같은 부동소수점 오류입니다.  기본 동작이 호출 프로그램을 종료합니다.  
  
 `SIGILL`  
 잘못된 명령.  기본 동작이 호출 프로그램을 종료합니다.  
  
 `SIGINT`  
 CTRL\+C 인터럽트  기본 작업은 종료 코드 3을 사용하여 호출하는 프로그램을 종료합니다.  
  
 `SIGSEGV`  
 잘못된 저장소 액세스.  기본 동작이 호출 프로그램을 종료합니다.  
  
 `SIGTERM`  
 전송 프로그램 종료 요청.  기본 작업은 종료 코드 3을 사용하여 호출하는 프로그램을 종료합니다.  
  
 `SIG_ERR`  
 반환 형식을 나타내는 신호에서 오류가 발생했습니다.  
  
## 참고 항목  
 [신호](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [전역 상수](../c-runtime-library/global-constants.md)