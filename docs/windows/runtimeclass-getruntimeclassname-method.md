---
title: "RuntimeClass::GetRuntimeClassName 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName 메서드"
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::GetRuntimeClassName 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 RuntimeClass 개체의 런타임 클래스 이름을 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
## 매개 변수  
 `runtimeName`  
 이 작업이 완료되면, 런타임 클래스 이름입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 \_\_WRL\_STRICT\_\_or \_\_WRL\_FORCE\_INSPECTABLE\_CLASS\_MACRO\_\_ 정의 되지 않은 경우 어설션 오류가 생성 됩니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)