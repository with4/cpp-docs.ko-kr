---
title: "Module::ReleaseNotifier::ReleaseNotifier 생성자 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier, 생성자"
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::ReleaseNotifier::ReleaseNotifier 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Module::ReleaseNotifier 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### 매개 변수  
 `release`  
 릴리스 메서드가 호출될 때 이 인스턴스를 삭제하기 위한 `true`, 이 인스턴스를 삭제하지 않는 `false`  
  
## 예외  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Module::ReleaseNotifier 클래스](../windows/module-releasenotifier-class.md)