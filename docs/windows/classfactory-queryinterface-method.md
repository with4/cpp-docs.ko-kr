---
title: "ClassFactory::QueryInterface 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface 메서드"
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ClassFactory::QueryInterface 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

매개 변수에 의해 지정된 인터페이스에 대한 포인터를 검색합니다.  
  
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
 이 작업이 완료되면, 매개변수 `riid` 로 지정된 인터페이스에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ClassFactory 클래스](../windows/classfactory-class.md)