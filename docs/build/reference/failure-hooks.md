---
title: "오류 후크 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "지연 DLL 로드, 오류 후크"
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 오류 후크
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류 후크는 [알림 후크](../../build/reference/notification-hooks.md)와 동일한 방식으로 활성화됩니다.  후크 루틴은 처리가 계속될 수 있도록 알맞은 값\(HINSTANCE 또는 FARPROC\)을 반환하거나 예외가 throw되어야 함을 알려주는 0을 반환해야 합니다.  
  
 사용자 정의 함수를 참조하는 포인터 변수는 다음과 같습니다.  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 **DelayLoadInfo** 구조체는 `GetLastError`의 값을 포함하여 오류를 정확히 보고하는 데 필요한 모든 데이터를 포함하고 있습니다.  
  
 알림이 **dliFailLoadLib**인 경우 후크 함수는 다음 값을 반환합니다.  
  
-   0 \- 오류를 처리할 수 없는 경우  
  
-   HMODULE \- 오류 후크가 문제를 수정하고 라이브러리 자체를 로드한 경우  
  
 알림이 **dliFailGetProc**인 경우 후크 함수는 다음 값을 반환합니다.  
  
-   0 \- 오류를 처리할 수 없는 경우  
  
-   올바른 프로시저 주소\(가져오기 함수 주소\) \- 오류 후크가 주소를 가져온 경우  
  
## 참고 항목  
 [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)