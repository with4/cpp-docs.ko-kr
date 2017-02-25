---
title: "AsyncBase::PutOnProgress 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::PutOnProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PutOnProgress 메서드"
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::PutOnProgress 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

진행률 이벤트 처리기의 주소를 지정된 된 값으로 설정합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   PutOnProgress  
)(TProgress* progressHandler);  
```  
  
#### 매개 변수  
 `progressHandler`  
 진행 중인 이벤트 처리기에 설정 된 주소입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 E\_ILLEGAL\_METHOD\_CALL입니다.  
  
## 요구 사항  
 **헤더:**  async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)