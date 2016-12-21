---
title: "CComMultiThreadModelNoCS Class | Microsoft Docs"
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
  - "ATL::CComMultiThreadModelNoCS"
  - "CComMultiThreadModelNoCS"
  - "ATL.CComMultiThreadModelNoCS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 다중 스레딩"
  - "CComMultiThreadModelNoCS class"
  - "스레딩[ATL]"
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComMultiThreadModelNoCS Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModelNoCS`스레드로부터 안전한 메서드 임계 영역 잠금 또는 잠금 해제 기능 없이 변수 값을 증가 및 감소를 제공합니다.  
  
## 구문  
  
```  
  
class CComMultiThreadModelNoCS  
  
```  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](../Topic/CComMultiThreadModelNoCS::AutoCriticalSection.md)|참조 클래스  [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComMultiThreadModelNoCS::CriticalSection](../Topic/CComMultiThreadModelNoCS::CriticalSection.md)|참조 클래스 `CComFakeCriticalSection`.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](../Topic/CComMultiThreadModelNoCS::ThreadModelNoCS.md)|참조 클래스 `CComMultiThreadModelNoCS`.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComMultiThreadModelNoCS::Decrement](../Topic/CComMultiThreadModelNoCS::Decrement.md)|\(정적\) 감소는 스레드로부터 안전한 방식으로 지정한 변수의 값입니다.|  
|[CComMultiThreadModelNoCS::Increment](../Topic/CComMultiThreadModelNoCS::Increment.md)|\(정적\) 스레드로부터 안전한 방식으로 지정한 변수의 값을 증가 시킵니다.|  
  
## 설명  
 `CComMultiThreadModelNoCS`유사한  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 는 변수 증가 및 감소에 대 한 스레드 안전한 방법을 제공 합니다.  그러나 참조할 때 임계 클래스를 통해 `CComMultiThreadModelNoCS`, 메서드 등 `Lock` 및 `Unlock` 아무 작업도 하지 것입니다.  
  
 일반적으로 사용 `CComMultiThreadModelNoCS` 통해는 `ThreadModelNoCS``typedef` 이름입니다.  이 `typedef` 에 정의 된 `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, 및  [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  전역 `typedef` 이름  [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) 및  [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) 를 참조 하지 않는 `CComMultiThreadModelNoCS`.  
  
 In addition to `ThreadModelNoCS`, `CComMultiThreadModelNoCS` defines `AutoCriticalSection` and `CriticalSection`.  후자의 두 `typedef` 참조 이름을  [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), 가져오기 및 중요 섹션을 해제와 관련 된 빈 메서드를 제공 합니다.  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)