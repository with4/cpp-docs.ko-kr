---
title: "call 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call 클래스"
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# call 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`call` 메시징 블록은 메시지를 받을 때 지정된 함수를 호출하는 다중 소스, 순서형 `target_block`입니다.  
  
## 구문  
  
```  
template<  
   class _Type,  
   class _FunctorType = std::tr1::function<void(_Type const&)>  
>  
class call : public target_block<multi_link_registry<ISource<_Type>>>;  
```  
  
#### 매개 변수  
 `_Type`  
 이 블록에 전파되는 메시지의 페이로드 형식입니다.  
  
 `_FunctorType`  
 이 블록이 받아들일 수 있는 함수의 서명입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[call::call 생성자](../Topic/call::call%20Constructor.md)|오버로드됨.  `call` 메시징 블록을 생성합니다.|  
|[call::~call 소멸자](../Topic/call::~call%20Destructor.md)|`call` 메시징 블록을 소멸시킵니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[call::process\_input\_messages 메서드](../Topic/call::process_input_messages%20Method.md)|입력된 메시지에서 호출 함수를 실행합니다.|  
|[call::process\_message 메서드](../Topic/call::process_message%20Method.md)|이 `call` 메시징 블록에서 수락한 메시지를 처리합니다.|  
|[call::propagate\_message 메서드](../Topic/call::propagate_message%20Method.md)|비동기적으로 메시지를 `ISource` 블록에서 이 `call` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `propagate` 메서드가 호출됩니다.|  
|[call::send\_message 메서드](../Topic/call::send_message%20Method.md)|동기적으로 메시지를 이 `ISource` 블록에서 이 `call` 메시징 블록에 전달합니다.  소스 블록에 의해 호출되면 `send` 메서드가 호출됩니다.|  
|[call::supports\_anonymous\_source 메서드](../Topic/call::supports_anonymous_source%20Method.md)|`supports_anonymous_source`  메서드를 재정의하여 이 블록에 연결 되지 않은 소스에서 제공하는 메시지를 사용할 수 있도록 표시합니다. \(재정의  [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md).\)|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [target\_block](../../../parallel/concrt/reference/target-block-class.md)  
  
 `call`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [transformer 클래스](../../../parallel/concrt/reference/transformer-class.md)