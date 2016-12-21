---
title: "ComPtr::operator!= 연산자 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator!="
dev_langs: 
  - "C++"
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator!= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 ComPtr 개체가 같지 않은지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### 매개 변수  
 `a`  
 ComPtr 개체에 대한 참조를 가져옵니다.  
  
 `b`  
 다른 ComPtr 개체에 대한 참조입니다.  
  
## 반환 값  
 만일 개체 `a` 가 개체 `b` 과 동일하지 않다면, 첫번째 연산자는 `true` 를 산출합니다. 그렇지 않으면 `false` 을 산출합니다.  
  
 만일 개체 `a` 가 `nullptr` 과 동일하지 않다면, 두 번째와 세 번째 연산자는 `true`를 산출합니다. 그렇지 않으면, `false` 을 산출합니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)   
 [ComPtr 클래스](../windows/comptr-class.md)