---
title: "CComSimpleThreadAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSimpleThreadAllocator"
  - "ATL::CComSimpleThreadAllocator"
  - "ATL.CComSimpleThreadAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL threads"
  - "ATL threads, 할당"
  - "CComSimpleThreadAllocator class"
  - "스레딩[ATL], selecting threads"
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComSimpleThreadAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 클래스에 대 한 스레드 선택 관리 `CComAutoThreadModule`.  
  
## 구문  
  
```  
  
class CComSimpleThreadAllocator  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComSimpleThreadAllocator::GetThread](../Topic/CComSimpleThreadAllocator::GetThread.md)|스레드를 선택합니다.|  
  
## 설명  
 `CComSimpleThreadAllocator`스레드 선택에 대 한 관리  [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  `CComSimpleThreadAllocator::GetThread`단순히 각 스레드를 통해 주기 및 다음 순서로 반환 합니다.  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [CComApartment Class](../../atl/reference/ccomapartment-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)