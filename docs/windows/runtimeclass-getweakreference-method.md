---
title: "RuntimeClass::GetWeakReference 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClass::GetWeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetWeakReference 메서드"
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass::GetWeakReference 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 런타임클래스 개체에 대한 약한 참조 개체에 대한 포인터를 갖습니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### 매개 변수  
 `weakReference`  
 이 작업을 완료시, 약한 참조 개체에 대한 포인터입니다.  
  
## 반환 값  
 항상 S\_OK입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)