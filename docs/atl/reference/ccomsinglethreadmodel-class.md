---
title: "CComSingleThreadModel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComSingleThreadModel"
  - "CComSingleThreadModel"
  - "ATL::CComSingleThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSingleThreadModel class"
  - "single-threaded applications"
  - "single-threaded applications, ATL"
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComSingleThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 메서드는 변수 값을 증가 및 감소에 대 한 제공합니다.  
  
## 구문  
  
```  
  
class CComSingleThreadModel  
  
```  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CComSingleThreadModel::AutoCriticalSection](../Topic/CComSingleThreadModel::AutoCriticalSection.md)|참조 클래스  [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](../Topic/CComSingleThreadModel::CriticalSection.md)|참조 클래스 `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](../Topic/CComSingleThreadModel::ThreadModelNoCS.md)|참조 `CComSingleThreadModel`.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComSingleThreadModel::Decrement](../Topic/CComSingleThreadModel::Decrement.md)|감소는 지정 된 변수의 값입니다.  이 구현 스레드로부터 안전 하지 않습니다.|  
|[CComSingleThreadModel::Increment](../Topic/CComSingleThreadModel::Increment.md)|지정 된 변수의 값을 증가 시킵니다.  이 구현 스레드로부터 안전 하지 않습니다.|  
  
## 설명  
 `CComSingleThreadModel`메서드는 변수 값을 증가 및 감소를 제공합니다.  달리  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및  [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), 이러한 메서드는 스레드로부터 안전 하지 않습니다.  
  
 일반적으로 사용 `CComSingleThreadModel` 둘 중 하나를 통해 `typedef` 는 이름  [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) 또는  [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  참조에서 각 클래스 `typedef` 다음 표와 같이 사용 하는 스레딩 모델에 따라 달라 집니다.  
  
|형식 정의|단일 스레딩 모델|아파트 스레딩 모델|자유 스레딩 모델|  
|-----------|---------------|----------------|---------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M \=`CComMultiThreadModel`  
  
 `CComSingleThreadModel`자체 세 정의 `typedef` 이름입니다.  `ThreadModelNoCS`참조 `CComSingleThreadModel`.  `AutoCriticalSection`및 `CriticalSection` 클래스를 참조  [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), 가져오기 및 중요 섹션의 소유권을 해제와 관련 된 빈 메서드를 제공 합니다.  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)