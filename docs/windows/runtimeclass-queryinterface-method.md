---
title: "RuntimeClass::QueryInterface 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface 메서드"
ms.assetid: 8f01f4a1-3fa2-4a8e-88c6-03629236cb9f
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::QueryInterface 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정한 인터페이스ID에 대한 포인터를 검색합니다.  
  
## 구문  
  
```  
  
STDMETHOD(  
   QueryInterface  
)  
   (REFIID riid,   
   _Deref_out_ void **ppvObject);  
```  
  
#### 매개 변수  
 `riid`  
 인터페이스 ID  
  
 `ppvObject`  
 이 작업이 완료될 때, 인터페이스에 대한 포인터는 `riid` 매개변수에 의해 지정됩니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)