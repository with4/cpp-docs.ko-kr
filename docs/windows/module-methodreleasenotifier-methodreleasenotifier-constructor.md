---
title: "Module::MethodReleaseNotifier::MethodReleaseNotifier 생성자 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier, 생성자"
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::MethodReleaseNotifier::MethodReleaseNotifier 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Module::MethodReleaseNotifier 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### 매개 변수  
 `object`  
 개체의 멤버 함수는 이벤트 처리기입니다.  
  
 `method`  
 이벤트 처리기인 매개 변수 `object` 의 멤버 함수.  
  
 `release`  
 `true` 를 [Module::ReleaseNotifier::Release\(\)](../windows/module-releasenotifier-release.md) 메서드를 사용하여 호출할 수 있게 지정합니다; 그렇지 않으면 `false` 를 지정합니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Module::MethodReleaseNotifier 클래스](../windows/module-methodreleasenotifier-class.md)