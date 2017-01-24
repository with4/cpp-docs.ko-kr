---
title: "CComAllocator Class | Microsoft Docs"
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
  - "ATL.CComAllocator"
  - "ATL::CComAllocator"
  - "CComAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAllocator class"
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 메모리 루틴을 사용 하 여 메모리를 관리 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
class CComAllocator  
  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComAllocator::Allocate](../Topic/CComAllocator::Allocate.md)|메모리를 할당할 수이 정적 메서드를 호출 합니다.|  
|[CComAllocator::Free](../Topic/CComAllocator::Free.md)|할당 된 메모리를 늘리려면이 정적 메서드를 호출 합니다.|  
|[CComAllocator::Reallocate](../Topic/CComAllocator::Reallocate.md)|메모리를 할당 하기 위하여이 정적 메서드를 호출 합니다.|  
  
## 설명  
 이 클래스를 사용 하 여  [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM 메모리 할당 루틴을 제공 합니다.  대응 클래스  [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), CRT 루틴이 사용 하는 동일한 메서드를 제공 합니다.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)