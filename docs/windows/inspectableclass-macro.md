---
title: "InspectableClass 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::InspectableClass"
dev_langs: 
  - "C++"
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# InspectableClass 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

런타임 클래스 이름 및 신뢰 수준을 설정합니다.  
  
## 구문  
  
```cpp  
  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
  
```  
  
#### 매개 변수  
 `runtimeClassName`  
 런타임 클래스의 전체 텍스트 이름입니다.  
  
 `trustLevel`  
 [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) 열거형 값 중 하나입니다.  
  
## 설명  
 `InspectableClass` 매크로는 단지 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 형식과 함께 사용할 수 있습니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)