---
title: "ITarget 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ITarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITarget 클래스"
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# ITarget 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`ITarget` 클래스는 모든 대상 블록의 인터페이스입니다.  대상 블록은 `ISource` 블록에서 제공한 메시지를 사용합니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class ITarget;  
```  
  
#### 매개 변수  
 `_Type`  
 대상 블록에서 허용되는 메시지 내의 페이로드 데이터 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`filter_method`|`bool` 값을 반환하여 제공된 메시지를 수락해야 할지 여부를 결정하는 블록에서 사용하는 메서드의 시그니처입니다.|  
|`type`|`_Type`에 대한 형식의 별칭입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[ITarget::~ITarget 소멸자](../Topic/ITarget::~ITarget%20Destructor.md)|`ITarget` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ITarget::propagate 메서드](../Topic/ITarget::propagate%20Method.md)|비동기적으로 메시지를 파생 클래스에서 재정의된 경우 이 대상 블록에 원본 블록에서 전달합니다.|  
|[ITarget::send 메서드](../Topic/ITarget::send%20Method.md)|파생 클래스에서 재정의된 경우 대상 블록에 메시지를 동기적으로 전달합니다.|  
|[ITarget::supports\_anonymous\_source 메서드](../Topic/ITarget::supports_anonymous_source%20Method.md)|파생 클래스에서 재정의 된 경우, 메시지 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할지 여부에 따라 true 또는 false를 반환합니다.  재정의 된 메서드는 `true`이 반환 된 경우 나중에 연기 메시지의 소비가 sourse 링크 레지스트리에 식별 할 수 있도록, 소스를 필요로하도록 대상은 제공된 메시지를 연기할 수 없습니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[ITarget::link\_source 메서드](../Topic/ITarget::link_source%20Method.md)|파생 클래스에서 재정의된 경우 지정한 소스 블록을 이 `ITarget` 블록에 연결합니다.|  
|[ITarget::unlink\_source 메서드](../Topic/ITarget::unlink_source%20Method.md)|파생 클래스에서 재정의된 경우 이 `ITarget` 블록에서 지정한 소스 블록을 연결 해제합니다.|  
|[ITarget::unlink\_sources 메서드](../Topic/ITarget::unlink_sources%20Method.md)|파생 클래스에서 재정의된 경우 이 `ITarget` 블록에서 모든 소스 블록의 연결을 해제합니다.|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 `ITarget`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource 클래스](../../../parallel/concrt/reference/isource-class.md)