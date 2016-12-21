---
title: "Implements::CastToUnknown 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Implements::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown 메서드"
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implements::CastToUnknown 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

근본적인 IUnknown 인터페이스에 대한 포인터입니다.  
  
## 구문  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## 반환 값  
 이 작업이 항상 성공하고 IUnknown 포인터를 반환 합니다.  
  
## 설명  
 내부 도우미 함수입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Implements 구조체](../windows/implements-structure.md)