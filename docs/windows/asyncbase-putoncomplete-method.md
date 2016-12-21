---
title: "AsyncBase::PutOnComplete 메서드 | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::PutOnComplete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PutOnComplete 메서드"
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::PutOnComplete 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

완료 이벤트 처리기의 주소를 지정된 된 값으로 설정합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   PutOnComplete  
)(TComplete* completeHandler);  
```  
  
#### 매개 변수  
 `completeHandler`  
 완료 이벤트 처리기에 설정 된 주소입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 E\_ILLEGAL\_METHOD\_CALL입니다.  
  
## 요구 사항  
 **헤더:**  async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)