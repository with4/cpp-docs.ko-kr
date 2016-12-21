---
title: "ActivationFactory::Release 메서드 | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release 메서드"
ms.assetid: 5bc25ff0-ee3c-4a2d-a9b6-2d8f158033ad
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactory::Release 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 ActivationFactory 개체의 참조 횟수를 감소 시킵니다.  
  
## 구문  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)