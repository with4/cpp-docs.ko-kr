---
title: "AsyncBase::GetOnProgress 메서드 | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::GetOnProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOnProgress 메서드"
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::GetOnProgress 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 된 변수를 현재 진행 중인 이벤트 처리기의 주소에 복사합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
#### 매개 변수  
 `progressHandler`  
 현재 진행 중인 이벤트 처리기의 주소가 저장 되어 있는 위치입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 E\_ILLEGAL\_METHOD\_CALL입니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)