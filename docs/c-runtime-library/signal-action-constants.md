---
title: "신호 작업 상수 | Microsoft Docs"
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
  - "SIG_IGN"
  - "SIG_DFL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIG_DFL 상수"
  - "SIG_IGN 상수"
  - "신호 동작 상수"
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 신호 작업 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터럽트 신호가 `func` 의 값에 따라 받아질 때, 작업이 수행됩니다.  
  
## 구문  
  
```  
#include <signal.h>  
```  
  
## 설명  
 `func` 인수는 함수의 주소 또는 아래 나열된 매니페스트 상수중 하나여야 하고, SIGNAL.H에서 정의됩니다.  
  
 `SIG_DFL`  
 시스템 기본값을 사용합니다.  만일 호출 프로그램이 스트림 I\/O를 사용하면, 런타임 라이브러리에 의해 만들어진 버퍼는 플러시되지 않습니다.  
  
 `SIG_IGN`  
 인터럽트 신호를 무시합니다.  이 값은 프로스세의 부동 소수점 상태가 정의되지 않았기 때문에, `SIGFPE` 에 제공되지 않을 것입니다.  
  
 `SIG_SGE`  
 신호에서 발생된 오류를 나타냅니다.  
  
 `SIG_ACK`  
 수신된 답신을 나타냅니다.  
  
 `SIG_ERR`  
 반환 형식을 나타내는 신호에서 오류가 발생했습니다.  
  
## 참고 항목  
 [신호](../c-runtime-library/reference/signal.md)   
 [전역 상수](../c-runtime-library/global-constants.md)