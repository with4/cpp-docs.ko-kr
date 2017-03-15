---
title: "RoInitializeWrapper::RoInitializeWrapper 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# RoInitializeWrapper::RoInitializeWrapper 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RolnitializeWrapper 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
RoInitializeWrapper(  
   RO_INIT_TYPE flags)  
  
```  
  
#### 매개 변수  
 `flags`  
 제공하는 지원을 지정하는 RO\_INIT\_TYPE 열거형 중 하나는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]입니다.  
  
## 설명  
 RoInitializeWrapper 클래스는 Windows::Foundation::Initialize\(*flags*\)를 호출합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)