---
title: "queuing_mode 열거형 | Microsoft Docs"
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
  - "amprt/Concurrency::queuing_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queuing_mode 열거형"
ms.assetid: 8c641054-906d-40b3-bbb4-f62af9356a14
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queuing_mode 열거형
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

큐는 가속기에서 지원되는 모드를 지정합니다.  
  
## 구문  
  
```  
enum queuing_mode;  
```  
  
## 멤버  
  
### 값  
  
|Name|설명|  
|----------|--------|  
|`queuing_mode_immediate`|예를 들어 [parallel\_for\_each 함수\(C\+\+ AMP\)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)처럼 명령을 지정하는 큐 모드는 호출자에게 반환되는 즉시 해당 가속기 장치로 보내집니다.|  
|`queuing_mode_automatic`|[accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md) 개체에 해당하는 명령 큐에 넣을 명령을 지정하는 큐 모드입니다.  명령은 [accelerator\_view::flush](../Topic/accelerator_view::flush%20Method.md)가 호출될 때 장치에 전송됩니다.|  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)