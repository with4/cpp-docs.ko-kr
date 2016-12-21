---
title: "ComPtr::Detach 메서드 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach 메서드"
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::Detach 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

dl `ComPtr` 개체를 나타난 인터페이스로부터 분리합니다.  
  
## 구문  
  
```  
T* Detach();  
```  
  
## 반환 값  
 이 `ComPtr` 개체에 의해 나타난 인터페이스에 대한 포인터입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)