---
title: "Module::GenericReleaseNotifier::GenericReleaseNotifier 생성자 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier, 생성자"
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GenericReleaseNotifier::GenericReleaseNotifier 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Module::GenericReleaseNotifier 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### 매개 변수  
 `callback`  
 람다, 함수, 또는 괄호 연산자 함수를 호출할 수 있는 함수 포인터 이벤트 처리기 \(`()`\).  
  
 `release`  
 `true` 를 [Module::ReleaseNotifier::Release\(\)](../windows/module-releasenotifier-release.md) 메서드를 사용하여 호출할 수 있게 지정합니다; 그렇지 않으면 `false` 를 지정합니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Module::GenericReleaseNotifier 클래스](../windows/module-genericreleasenotifier-class.md)