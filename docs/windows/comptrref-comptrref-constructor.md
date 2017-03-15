---
title: "ComPtrRef::ComPtrRef 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRef, 생성자"
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtrRef::ComPtrRef 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
#### 매개 변수  
 `ptr`  
 다른 ComPtrRef 개체의 내부 값입니다.  
  
## 설명  
 다른 ComPtrRef 개체에 지정된 된 포인터를 ComPtrRef 클래스의 새 인스턴스를 초기화합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [ComPtrRef 클래스](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)