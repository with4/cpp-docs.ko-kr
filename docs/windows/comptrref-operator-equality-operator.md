---
title: "ComPtrRef::operator== 연산자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator=="
dev_langs: 
  - "C++"
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator== 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```cpp  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### 매개 변수  
 `a`  
 ComPtrRef개체에 대한 참조를 가져옵니다.  
  
 `b`  
 익명 형식에 대한 포인터 또는 다른 ComPtrRef 개체에 대한 참조 \(`void*`\).  
  
## 반환 값  
 만일 개체 `a` 가 개체 `b` 과 동일하다면, 첫번째 연산자는 `true` 를 산출합니다. 그렇지 않으면 `false` 을 산출합니다.  
  
 만일 개체 `a` 가 `nullptr` 과 동일하다면, 두 번째와 세 번째 연산자는 `true`를 산출합니다. 그렇지 않으면, `false` 을 산출합니다.  
  
 개체 `a` 가 개체 `b` 과 동일하다면, 네 번째 와 다섯 번째 연산자는 `true` 입니다, 그렇지 않으면, `false` 입니다.  
  
## 설명  
 ComPtrRef 개체가 같지 않은지 여부를 나타냅니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef 클래스](../windows/comptrref-class.md)