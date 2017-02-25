---
title: "message 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message 클래스"
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# message 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

메시징 블록 사이에 전달되는 데이터 페이로드를 포함하는 기본 메시지 Envelope입니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class message : public ::Concurrency::details::_Runtime_object;  
```  
  
#### 매개 변수  
 `_Type`  
 메시지 내의 페이로드 데이터 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`type`|`_Type`에 대한 형식의 별칭입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[message::message 생성자](../Topic/message::message%20Constructor.md)|오버로드됨.  `message` 개체를 생성합니다.|  
|[message::~message 소멸자](../Topic/message::~message%20Destructor.md)|`message` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[message::add\_ref 메서드](../Topic/message::add_ref%20Method.md)|`message` 개체에 대한 참조 횟수에 추가합니다.  메시지 수명을 확인하려면 참조 횟수가 필요한 메시지 블록에 사용됩니다.|  
|[message::msg\_id 메서드](../Topic/message::msg_id%20Method.md)|`message` 개체의 ID를 반환합니다.|  
|[message::remove\_ref 메서드](../Topic/message::remove_ref%20Method.md)|`message` 개체에 대한 참조 횟수에서 뺍니다.  메시지 수명을 확인하려면 참조 횟수가 필요한 메시지 블록에 사용됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[message::payload 데이터 멤버](../Topic/message::payload%20Data%20Member.md)|`message` 개체의 페이로드입니다.|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 `message`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)