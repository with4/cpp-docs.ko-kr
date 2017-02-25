---
title: "CCRTAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCRTAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTAllocator class"
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCRTAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 CRT 메모리 루틴을 사용 하 여 메모리를 관리 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
class ATL::CCRTAllocator  
  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CCRTAllocator::Allocate](../Topic/CCRTAllocator::Allocate.md)|\(정적\) 메모리를 할당 하는 데이 메서드를 호출 합니다.|  
|[CCRTAllocator::Free](../Topic/CCRTAllocator::Free.md)|\(정적\) 메모리를 해제 하려면이 메서드를 호출 합니다.|  
|[CCRTAllocator::Reallocate](../Topic/CCRTAllocator::Reallocate.md)|\(정적\) 메모리를 다시 할당 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 이 클래스를 사용 하 여  [CHeapPtr](../../atl/reference/cheapptr-class.md) CRT 메모리 할당 루틴을 제공 합니다.  대응 클래스  [CComAllocator](../../atl/reference/ccomallocator-class.md), COM 루틴을 사용 하 여 동일한 메서드를 제공 합니다.  
  
## 요구 사항  
 **헤더:** atlcore.h  
  
## 참고 항목  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComAllocator Class](../../atl/reference/ccomallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)