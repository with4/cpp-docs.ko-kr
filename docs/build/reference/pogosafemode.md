---
title: "PogoSafeMode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PogoSafeMode"
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# PogoSafeMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빠른 모드 또는 안전 모드를 응용 프로그램 프로파일링에 사용할지 여부를 지정합니다.  
  
## 구문  
  
```  
PogoSafeMode  
```  
  
## 설명  
 PGO\(프로필 기반 최적화\)에는 프로파일링 단계에서 가능한 빠른 모드와 안전 모드 두 가지 모드가 있습니다.  프로파일링이 빠른 모드에 있을 때 데이터 카운터를 늘리려면 **INC** 명령을 사용합니다.  **INC** 명령은 빠르지만 스레드로부터 안전하게 보호되지 않습니다.  프로파일링이 안전 모드에 있을 때 데이터 카운터를 늘리려면 **LOCK INC** 명령을 사용합니다.  **LOCK INC** 명령에는 **INC** 명령에 있는 것과 같은 기능이 있으며 스레드로부터 안전하게 보호되지만 **INC** 명령보다는 느립니다.  
  
 기본적으로 PGO 프로파일링은 빠른 모드로 작동합니다.  `PogoSafeMode`는 안전 모드를 사용할 경우에만 필요합니다.  
  
 안전 모드에서 PGO 프로파일링을 실행하려면 시스템에 따라 환경 변수 `PogoSafeMode` 또는 링커 스위치 **\-PogoSafeMode**를 사용해야 합니다.  x64 컴퓨터에서 프로파일링을 수행하는 경우 링커 스위치를 사용해야 합니다.  x86 컴퓨터에서 프로파일링을 수행하는 경우 최적화 프로세스를 시작하기 전에 모든 값으로 환경 변수를 정의해야 합니다.  
  
## 예제  
  
```  
set PogoSafeMode=1  
```  
  
## 참고 항목  
 [프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)