---
title: "ComPtrRef::GetAddressOf 메서드 | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddressOf 메서드"
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::GetAddressOf 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
InterfaceType* const * GetAddressOf() const;  
```  
  
## 반환 값  
 현재 ComPtrRef 개체를 나타내는 인터페이스에 대한 포인터 주소입니다.  
  
## 설명  
 현재 ComPtrRef 개체로 표시되는 인터페이스에 대한 포인터의 주소를 검색합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [ComPtrRef 클래스](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)