---
title: "ComPtrRef::ReleaseAndGetAddressOf 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf 메서드"
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtrRef::ReleaseAndGetAddressOf 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
InterfaceType** ReleaseAndGetAddressOf();  
```  
  
## 반환 값  
 삭제된 ComPtrRef 개체를 나타내는 인터페이스 포인터입니다.  
  
## 설명  
 현재 ComPtrRef 개체를 삭제하고 ComPtrRef 개체로 표시되는 인터페이스 포인터\-에\-a\-포인터를 반환합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [ComPtrRef 클래스](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)