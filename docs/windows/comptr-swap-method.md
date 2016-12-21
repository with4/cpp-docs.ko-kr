---
title: "ComPtr::Swap 메서드 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::Swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Swap 메서드"
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::Swap 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 ComPtr에 의해 관리되는 인터페이스를 사용하여 현재 ComPtr에 의해 관리되는 인터페이스를 교환합니다.  
  
## 구문  
  
```  
void Swap(  
   _Inout_ ComPtr&& r  
);  
  
void Swap(  
   _Inout_ ComPtr& r  
);  
```  
  
#### 매개 변수  
 `r`  
 ComPtr.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)