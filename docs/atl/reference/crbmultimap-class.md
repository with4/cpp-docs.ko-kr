---
title: "CRBMultiMap Class | Microsoft Docs"
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
  - "CRBMultiMap"
  - "ATL.CRBMultiMap"
  - "ATL::CRBMultiMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMultiMap class"
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMultiMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 각 키 빨강 검정 이진 트리를 사용 하 여 둘 이상의 값을 연결할 수 있도록 매핑 구조체를 나타냅니다.  
  
## 구문  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBMultiMap : public CRBTree< K, V, KTraits, VTraits >  
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
|[CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md)|생성자입니다.|  
|[CRBMultiMap::~CRBMultiMap](../Topic/CRBMultiMap::~CRBMultiMap.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md)|지정 된 키와 첫 번째 요소의 위치를 찾기 위해이 메서드를 호출 합니다.|  
|[CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md)|지정 된 키와 관련 값을 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.|  
|[CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md)|이 메서드는 지정 된 키와 연결 된 요소를 호출 하 고 위치 값을 업데이트 합니다.|  
|[CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md)|지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|  
|[CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md)|특정된 키에 대 한 키\/값 요소를 모두 제거 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CRBMultiMap`매핑 배열을 순서화 된 배열을 핵심 요소와 값을 관리 하는 특정된 형식에 대 한 지원 합니다.  달리는  [CRBMap](../../atl/reference/crbmap-class.md) 클래스, 각 키 수 둘 이상의 값을 연결 합니다.  
  
 이진 트리에서 요소 \(키와 값으로 구성 된\) 저장 구조를 사용 하 여  [CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md) 메서드.  요소를 사용 하 여 제거할 수 있습니다는  [CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md) 지정 된 키와 일치 하는 모든 요소를 삭제 하는 방법.  
  
 트리를 검색 한 가능한 메서드와 같이  [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md),  [CRBTree::GetNext](../Topic/CRBTree::GetNext.md), 및  [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md).  액세스 하는 키 마다 여러 값 잠재적으로 사용 가능한은  [CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md),  [CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md), 및  [CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md) 메서드.  예제를 보려면  [CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md) 에서는 이러한 연습에서을 합니다.  
  
 `KTraits` 및 `VTraits` 매개 변수는 특성 클래스 요소를 옮기거나 복사 하는 데 필요한 추가 코드가 포함 되어 있습니다.  
  
 `CRBMultiMap`파생 된  [CRBTree](../../atl/reference/crbtree-class.md), 빨강, 검정 알고리즘을 사용 하는 이진 트리를 구현 합니다.  대신 `CRBMultiMap` 및 `CRBMap` 에서 제공 되는  [CAtlMap](../../atl/reference/catlmap-class.md) 클래스.  만 적은 수의 요소를 저장 해야 하는 경우 사용 하는 것은  [CSimpleMap](../../atl/reference/csimplemap-class.md) 대신 클래스.  
  
 컬렉션 클래스는 다양 한 기능 및 성능 특성에 대 한 자세한 설명은 참조 하십시오  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMap Class](../../atl/reference/crbmap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)