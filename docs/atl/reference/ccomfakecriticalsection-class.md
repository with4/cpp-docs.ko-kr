---
title: "CComFakeCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComFakeCriticalSection"
  - "CComFakeCriticalSection"
  - "ATL::CComFakeCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComFakeCriticalSection class"
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComFakeCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 동일한 방법으로 제공  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 임계 영역을 제공 하지 않지만.  
  
## 구문  
  
```  
  
class CComFakeCriticalSection  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComFakeCriticalSection::Init](../Topic/CComFakeCriticalSection::Init.md)|없는 임계 이므로 아무 작업도 하지 않습니다.|  
|[CComFakeCriticalSection::Lock](../Topic/CComFakeCriticalSection::Lock.md)|없는 임계 이므로 아무 작업도 하지 않습니다.|  
|[CComFakeCriticalSection::Term](../Topic/CComFakeCriticalSection::Term.md)|없는 임계 이므로 아무 작업도 하지 않습니다.|  
|[CComFakeCriticalSection::Unlock](../Topic/CComFakeCriticalSection::Unlock.md)|없는 임계 이므로 아무 작업도 하지 않습니다.|  
  
## 설명  
 `CComFakeCriticalSection`미러링에 메서드  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  그러나 `CComFakeCriticalSection` ; 임계 제공 하지 않습니다 따라서 해당 메서드는 그대로 둡니다.  
  
 일반적으로 사용 `CComFakeCriticalSection` 통해는 `typedef` , 이름 `AutoCriticalSection` 또는 `CriticalSection`.  사용 하는 경우  [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 또는  [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), 둘 다 `typedef` 참조의 이름을 `CComFakeCriticalSection`.  사용 하는 경우  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)을 참조  [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) 및 `CComCriticalSection`, 각각.  
  
## 요구 사항  
 **헤더:** atlcore.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)