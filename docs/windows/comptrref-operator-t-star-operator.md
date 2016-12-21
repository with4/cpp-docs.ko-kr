---
title: "ComPtrRef::operator T* 연산자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator T*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator T* 연산자"
ms.assetid: b4f83370-0ebc-4d56-87c6-1a8ea2d0079b
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator T* 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
operator T*();  
```  
  
## 설명  
 현재 ComPtrRef 개체의 [ptr\_](../windows/comptrrefbase-ptr-data-member.md) 데이터 멤버의 값을 반환합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [ComPtrRef 클래스](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)