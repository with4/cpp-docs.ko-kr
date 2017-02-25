---
title: "ActivationFactory::QueryInterface 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface 메서드"
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::QueryInterface 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정한 인터페이스에 대한 포인터를 검색합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
#### 매개 변수  
 `riid`  
 인터페이스 ID  
  
 `ppvObject`  
 이 작업이 완료될 때, 매개변수 `riid` 로 지정된 인터페이스에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)