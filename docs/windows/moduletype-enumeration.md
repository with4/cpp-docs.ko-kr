---
title: "ModuleType 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ModuleType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleType 열거형"
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ModuleType 열거형
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로세스에서 서버 또는 독립 프로세스 서버 모듈을 지원하는지 여부를 지정합니다.  
  
## 구문  
  
```  
enum ModuleType;  
```  
  
## 멤버  
  
### 값  
  
|Name|설명|  
|----------|--------|  
|`InProc`|in\-process 서버.|  
|`OutOfProc`|독립 프로세스 서버입니다.|  
|`DisableCaching`|모듈에 대한 캐싱 메커니즘을 사용하지 않습니다.|  
|`InProcDisableCaching`|`InProc` 및 `DisableCaching`의 조합입니다.|  
|`OutOfProcDisableCaching`|`OutOfProc` 및 `DisableCaching`의 조합입니다.|  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)