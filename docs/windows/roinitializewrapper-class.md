---
title: "RoInitializeWrapper 클래스 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RoInitializeWrapper 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]을 초기화합니다.  
  
## 구문  
  
```  
class RoInitializeWrapper  
```  
  
## 설명  
 RoInitializeWrapper는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 를 초기화하는 편의를 제공하고 작업이 성공적인지를 나타내는 HRESULT를 반환합니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[RoInitializeWrapper::RoInitializeWrapper 생성자](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|RolnitializeWrapper 클래스의 새 인스턴스를 초기화합니다.|  
|[RoInitializeWrapper::~RoInitializeWrapper 소멸자](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|RolnitializeWrapper 클래스의 현재 인스턴스를 제거합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[RoInitializeWrapper::HRESULT\(\) 연산자](../windows/roinitializewrapper-hresult-parens-operator.md)|RoInitializeWrapper 생성자에 의해 생성된 HRESULT 값을 검색합니다.|  
  
## 상속 계층  
 `RoInitializeWrapper`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)