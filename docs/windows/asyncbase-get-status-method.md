---
title: "AsyncBase::get_Status 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_Status"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_Status 메서드"
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::get_Status 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업의 상태를 나타내는 값을 검색합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   get_Status  
)(AsyncStatus *status) override;  
```  
  
#### 매개 변수  
 `status`  
 상태가 저장되어는 위치입니다.  더많은 정보는 Windows::Foundation::AsynStatus 열거형을 참조하십시오.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 E\_ILLEGAL\_METHOD\_CALL입니다.  
  
## 설명  
 이 메서드는 IAsyncInfo::get\_Status 를 구현합니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)