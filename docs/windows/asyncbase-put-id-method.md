---
title: "AsyncBase::put_Id 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::put_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "put_Id 메서드"
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::put_Id 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업에 대한 핸들을 설정합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   put_Id  
)(const unsigned int id);  
```  
  
#### 매개 변수  
 `id`  
 0이 아닌 핸들입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 E\_INVALIDARG 또는 E\_ILLEGAL\_METHOD\_CALL입니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)