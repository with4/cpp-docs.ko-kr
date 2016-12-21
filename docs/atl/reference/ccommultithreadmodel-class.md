---
title: "CComMultiThreadModel Class | Microsoft Docs"
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
  - "CComMultiThreadModel"
  - "ATL.CComMultiThreadModel"
  - "ATL::CComMultiThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 다중 스레딩"
  - "CComMultiThreadModel class"
  - "스레딩[ATL]"
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComMultiThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModel`스레드로부터 안전한 방법 증가 및 감소에 대 한 변수 값을 제공합니다.  
  
## 구문  
  
```  
  
class CComMultiThreadModel  
  
```  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CComMultiThreadModel::AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)|참조 클래스  [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|  
|[CComMultiThreadModel::CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md)|참조 클래스  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|  
|[CComMultiThreadModel::ThreadModelNoCS](../Topic/CComMultiThreadModel::ThreadModelNoCS.md)|참조 클래스  [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComMultiThreadModel::Decrement](../Topic/CComMultiThreadModel::Decrement.md)|\(정적\) 감소는 스레드로부터 안전한 방식으로 지정한 변수의 값입니다.|  
|[CComMultiThreadModel::Increment](../Topic/CComMultiThreadModel::Increment.md)|\(정적\) 스레드로부터 안전한 방식으로 지정한 변수의 값을 증가 시킵니다.|  
  
## 설명  
 일반적으로 사용 `CComMultiThreadModel` 둘 중 하나를 통해 `typedef` 는 이름  [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) 또는  [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  참조에서 각 클래스 `typedef` 다음 표와 같이 사용 하는 스레딩 모델에 따라 달라 집니다.  
  
|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|  
|-----------|------------|-------------|------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M \=`CComMultiThreadModel`  
  
 `CComMultiThreadModel`자체 세 정의 `typedef` 이름입니다.  `AutoCriticalSection`및 `CriticalSection` 얻고 중요 섹션의 소유권을 해제에 대 한 메서드를 제공 하는 클래스를 참조 합니다.  `ThreadModelNoCS`참조 클래스  [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [CComSingleThreadModel Class](../../atl/reference/ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)