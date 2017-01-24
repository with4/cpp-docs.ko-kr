---
title: "Module::ReleaseNotifier::Invoke 메서드 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::ReleaseNotifier::Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Invoke 메서드"
ms.assetid: f62686fe-74bf-482b-a46b-6a3c09b80e7e
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::ReleaseNotifier::Invoke 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

구현 될 때, 모듈의 마지막 개체가 해제 될 때 이벤트 처리기를 호출 합니다.  
  
## 구문  
  
```  
virtual void Invoke() = 0;  
```  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Module::ReleaseNotifier 클래스](../windows/module-releasenotifier-class.md)