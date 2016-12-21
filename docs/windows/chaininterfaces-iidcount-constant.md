---
title: "ChainInterfaces::IidCount 상수 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::IidCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IidCount 상수"
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::IidCount 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스 ID의 총 수는 `I9` 를 통한 인터페이스에서 템플릿 매개변수 `I0` 로 지정됨을 포함합니다.  
  
## 구문  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## 반환 값  
 인터페이스 Id의 총 수입니다.  
  
## 설명  
 템플릿 매개변수 `I0` 및 `I1` 는 필요로 되고 매개변수 `I2`은 `I9` 을 통해 선택사항입니다. 각 인터페이스의 IID의 수는 보통 1입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)