---
title: "ISource 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ISource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISource 클래스"
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# ISource 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`ISource` 클래스는 모든 소스 블록의 인터페이스입니다.  소스 블록은 소스 `ITarget` 블록에 메시지를 전파합니다.  
  
## 구문  
  
```  
template<  
   class _Type  
>  
class ISource;  
```  
  
#### 매개 변수  
 `_Type`  
 소스 블록에 의해 생성된 메시지 내의 페이로드 데이터 형식입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`source_type`|`_Type`에 대한 형식의 별칭입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[ISource::~ISource 소멸자](../Topic/ISource::~ISource%20Destructor.md)|`ISource` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ISource::accept 메서드](../Topic/ISource::accept%20Method.md)|파생된 클래스에서 재정의될 때 호출자에서 소유권을 전송하여 이 `ISource` 블록에서 제공된 메시지를 수락합니다.|  
|[ISource::acquire\_ref 메서드](../Topic/ISource::acquire_ref%20Method.md)|파생 클래스에서 재정의된 경우 삭제가 발생하지 않도록 이 `ISource` 블록에서 참조 횟수를 가져옵니다.|  
|[ISource::consume 메서드](../Topic/ISource::consume%20Method.md)|파생된 클래스에서 재정의되면 이 `ISource` 블록에서 이전에 제공되고 호출자에게 소유권을 전송하여 대상에 의해 예약된 메시지를 사용합니다.|  
|[ISource::link\_target 메서드](../Topic/ISource::link_target%20Method.md)|파생 클래스에서 재정의된 경우 대상 블록을 이 `ISource` 블록에 연결합니다.|  
|[ISource::release 메서드](../Topic/ISource::release%20Method.md)|파생 클래스에서 재정의된 경우 이전의 성공적인 메시지 예약을 해제합니다.|  
|[ISource::release\_ref 메서드](../Topic/ISource::release_ref%20Method.md)|파생 클래스에서 재정의된 경우 이 `ISource` 블록에서 참조 횟수를 해제합니다.|  
|[ISource::reserve 메서드](../Topic/ISource::reserve%20Method.md)|파생 클래스에서 재정의된 경우 이 `ISource` 블록에서 이전에 제공했던 메시지를 예약합니다.|  
|[ISource::unlink\_target 메서드](../Topic/ISource::unlink_target%20Method.md)|파생 클래스에서 재정의된 경우 이전에 연결이 발견되면 이 `ISource` 블록에서 대상 블록의 연결을 해제합니다.|  
|[ISource::unlink\_targets 메서드](../Topic/ISource::unlink_targets%20Method.md)|파생 클래스에서 재정의된 경우 이 `ISource` 블록에서 모든 대상 블록의 연결을 해제합니다.|  
  
## 설명  
 자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)을 참조하십시오.  
  
## 상속 계층  
 `ISource`  
  
## 요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget 클래스](../../../parallel/concrt/reference/itarget-class.md)