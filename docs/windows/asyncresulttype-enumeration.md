---
title: "AsyncResultType 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncResultType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncResultType 열거형"
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncResultType 열거형
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

GetResults\(\) 메서드에 의해 반환된 결과의 형식을 지정합니다.  
  
## 구문  
  
```  
enum AsyncResultType;  
```  
  
## 멤버  
  
### 값  
  
|Name|설명|  
|----------|--------|  
|`MultipleResults`|제공된 점진적으로 시작 상태 및 close \(\)를 호출하기 전에 여러 결과의 집합입니다.|  
|`SingleResult`|단일 결과 완료 이벤트가 발생 한 후에 표시 됩니다.|  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)