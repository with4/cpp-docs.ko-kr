---
title: "ComPtr::GetAddressOf 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddressOf 메서드"
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ComPtr::GetAddressOf 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ptr\_](../windows/comptr-ptr-data-member.md) 데이터 멤버의 주소를 검색합니다, 이는 이 ComPtr에 의해 표현된 인터페이스에 대한 포인터를 포함합니다.  
  
## 구문  
  
```  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## 반환 값  
 변수의 주소  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)