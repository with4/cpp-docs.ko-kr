---
title: "ClassFactory::AddRef 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory::AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef 메서드"
ms.assetid: 5b091785-dea4-42b6-a502-0db5fc7a5a2e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ClassFactory::AddRef 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 ClassFactory 개체의 참조 횟수를 증가시킵니다.  
  
## 구문  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ClassFactory 클래스](../windows/classfactory-class.md)