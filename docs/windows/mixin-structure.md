---
title: "MixIn 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::MixIn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MixIn 구조체"
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MixIn 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 및 클래식 COM 인터페이스일 경으, [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 인터페이스로부터 런타임 클래스가 도출됨을 확인합니다.  
  
## 구문  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### 매개 변수  
 `Derived`  
 [구현](../windows/implements-structure.md) 구조체로부터 도출된 형식.  
  
 `MixInType`  
 기본 형식입니다.  
  
 `hasImplements`  
 만일 `MixInType` 가 현재 실행하는 기본 형식으로부터 도출된 경우, `true`, 그렇지 않으면 `false`  
  
## 설명  
 클래스가 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 및 클래스 COM 인터페이스 둘다 도출된 경우, 클래스 선언 목록은 모든 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 인터페이스와 모든 클래식 COM 인터페이스를 첫 번째로 목록화합니다.  MixIn 순서에 따라 인터페이스를 지정하면 됩니다.  
  
## 상속 계층  
 `MixIn`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)