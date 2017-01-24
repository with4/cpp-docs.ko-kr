---
title: "CRBMap Class | Microsoft Docs"
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
  - "ATL.CRBMap"
  - "CRBMap"
  - "ATL::CRBMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMap class"
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 빨강\-검정 이진 트리를 사용 하 여 매핑 구조체를 나타냅니다.  
  
## 구문  
  
```  
  
      template<   
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >   
> class CRBMap : public CRBTree< K, V, KTraits, VTraits >  
```  
  
#### 매개 변수  
 `K`  
 키 요소 형식입니다.  
  
 *V*  
 값 요소 형식입니다.  
  
 `KTraits`  
 복사 또는 키 요소를 이동 하는 데 사용 되는 코드입니다.  참조  [CElementTraits 클래스](../../atl/reference/celementtraits-class.md) 에 대 한 자세한 내용은.  
  
 `VTraits`  
 요소 값을 옮기거나 복사 하는 데 사용 되는 코드입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRBMap::CRBMap](../Topic/CRBMap::CRBMap.md)|생성자입니다.|  
|[CRBMap::~CRBMap](../Topic/CRBMap::~CRBMap.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRBMap::Lookup](../Topic/CRBMap::Lookup.md)|키 또는 값을 조회 하도록이 메서드를 호출 하 여 `CRBMap` 개체입니다.|  
|[CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md)|요소를 제거 하려면이 메서드를 호출 하는 `CRBMap` 키를 지정 된 개체를.|  
|[CRBMap::SetAt](../Topic/CRBMap::SetAt.md)|지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CRBMap`핵심 요소 및 관련된 값의 정렬 된 배열을 관리 하는 특정된 형식 매핑 배열을를 지원 합니다.  각 키 관련된 값을 하나만 가질 수 있습니다.  이진 트리에서 요소 \(키와 값으로 구성 된\) 저장 구조를 사용 하 여  [CRBMap::SetAt](../Topic/CRBMap::SetAt.md) 메서드.  요소를 사용 하 여 제거할 수 있습니다는  [CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md) 요소에 지정 된 키 값을 삭제 하는 방법.  
  
 트리를 검색 한 가능한 메서드와 같이  [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md),  [CRBTree::GetNext](../Topic/CRBTree::GetNext.md), 및  [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md).  
  
 `KTraits` 및 `VTraits` 매개 변수는 특성 클래스 요소를 옮기거나 복사 하는 데 필요한 추가 코드가 포함 되어 있습니다.  
  
 `CRBMap`파생 된  [CRBTree](../../atl/reference/crbtree-class.md), 빨강, 검정 알고리즘을 사용 하는 이진 트리를 구현 합니다.  [CRBMultiMap](../../atl/reference/crbmultimap-class.md) 각 키에 대해 여러 값을 허용 하는 변형입니다.  너무에서 파생 된 `CRBTree`, 너무 많은 기능을 공유 하 고 `CRBMap`.  
  
 대신 모두 `CRBMap` 및 `CRBMultiMap` 에서 제공 되는  [CAtlMap](../../atl/reference/catlmap-class.md) 클래스.  만 적은 수의 요소를 저장 해야 하는 경우 사용 하는 것은  [CSimpleMap](../../atl/reference/csimplemap-class.md) 대신 클래스.  
  
 컬렉션 클래스는 다양 한 기능 및 성능 특성에 대 한 자세한 설명은 참조 하십시오  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap Class](../../atl/reference/crbmultimap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)