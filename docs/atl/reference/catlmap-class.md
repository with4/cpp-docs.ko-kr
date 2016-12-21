---
title: "CAtlMap Class | Microsoft Docs"
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
  - "ATL.CAtlMap"
  - "CAtlMap"
  - "ATL::CAtlMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlMap class"
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 만들고 맵 개체를 관리 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
>  
class CAtlMap  
```  
  
#### 매개 변수  
 `K`  
 키 요소 형식입니다.  
  
 V  
 값 요소 형식입니다.  
  
 `KTraits`  
 복사 또는 키 요소를 이동 하는 데 사용 되는 코드입니다.  참조  [CElementTraits 클래스](../../atl/reference/celementtraits-class.md) 에 대 한 자세한 내용은.  
  
 `VTraits`  
 요소 값을 옮기거나 복사 하는 데 사용 되는 코드입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CAtlMap::KINARGTYPE](../Topic/CAtlMap::KINARGTYPE.md)|키 입력된 인수로 전달 될 때 사용 되는 형식|  
|[CAtlMap::KOUTARGTYPE](../Topic/CAtlMap::KOUTARGTYPE.md)|키를 출력 인수로 반환 될 때 사용 되는 형식입니다.|  
|[CAtlMap::VINARGTYPE](../Topic/CAtlMap::VINARGTYPE.md)|값을 입력된 인수로 전달 될 때 사용 되는 형식입니다.|  
|[CAtlMap::VOUTARGTYPE](../Topic/CAtlMap::VOUTARGTYPE.md)|값 출력 인수로 전달 될 때 사용 되는 형식입니다.|  
  
### 공용 클래스  
  
|Name|설명|  
|----------|--------|  
|[CAtlMap::CPair Class](../Topic/CAtlMap::CPair%20Class.md)|키 \/ 값 요소를 포함 하는 클래스입니다.|  
  
### CPair 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPair::m\_key](../Topic/CAtlMap::CPair::m_key.md)|키 요소를 저장할 데이터 멤버입니다.|  
|[CPair::m\_value](../Topic/CAtlMap::CPair::m_value.md)|데이터 멤버 값 요소를 저장 합니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlMap::CAtlMap](../Topic/CAtlMap::CAtlMap.md)|생성자입니다.|  
|[CAtlMap::~CAtlMap](../Topic/CAtlMap::~CAtlMap.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlMap::AssertValid](../Topic/CAtlMap::AssertValid.md)|경우 어설션을 인해이 메서드를 호출 하는 `CAtlMap` 유효 하지 않습니다.|  
|[CAtlMap::DisableAutoRehash](../Topic/CAtlMap::DisableAutoRehash.md)|자동 해싱하여 사용 하지 않으려면이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
|[CAtlMap::EnableAutoRehash](../Topic/CAtlMap::EnableAutoRehash.md)|자동 해싱하여 사용할 수 있도록이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
|[CAtlMap::GetAt](../Topic/CAtlMap::GetAt.md)|지도에서 지정 된 위치에서 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::GetCount](../Topic/CAtlMap::GetCount.md)|맵에 있는 요소의 개수를 검색 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::GetHashTableSize](../Topic/CAtlMap::GetHashTableSize.md)|저장소의 맵 해시 테이블에서의 수를 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::GetKeyAt](../Topic/CAtlMap::GetKeyAt.md)|지정 된 위치에 저장 된 키를 검색 하려면이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
|[CAtlMap::GetNext](../Topic/CAtlMap::GetNext.md)|쌍을 저장에서 다음 요소에 대 한 포인터를 가져오려면이 메서드를 호출 하 여 `CAtlMap` 개체입니다.|  
|[CAtlMap::GetNextAssoc](../Topic/CAtlMap::GetNextAssoc.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CAtlMap::GetNextKey](../Topic/CAtlMap::GetNextKey.md)|다음 키를 검색 하려면이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
|[CAtlMap::GetNextValue](../Topic/CAtlMap::GetNextValue.md)|다음 값을 가져오려면이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
|[CAtlMap::GetStartPosition](../Topic/CAtlMap::GetStartPosition.md)|맵 반복 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::GetValueAt](../Topic/CAtlMap::GetValueAt.md)|지정 된 위치에 저장 된 값을 검색 하려면이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
|[CAtlMap::InitHashTable](../Topic/CAtlMap::InitHashTable.md)|해시 테이블을 초기화 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::IsEmpty](../Topic/CAtlMap::IsEmpty.md)|빈 지도 개체를 테스트 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::Lookup](../Topic/CAtlMap::Lookup.md)|키 또는 값을 조회 하도록이 메서드를 호출 하 여 `CAtlMap` 개체입니다.|  
|[CAtlMap::Rehash](../Topic/CAtlMap::Rehash.md)|다루어진이 메서드를 호출 하 여 `CAtlMap` 개체입니다.|  
|[CAtlMap::RemoveAll](../Topic/CAtlMap::RemoveAll.md)|모든 요소를 제거 하려면이 메서드를 호출 하 여 `CAtlMap` 개체입니다.|  
|[CAtlMap::RemoveAtPos](../Topic/CAtlMap::RemoveAtPos.md)|지정 된 위치에서 요소를 제거 하려면이 메서드를 호출 하는 `CAtlMap` 개체.|  
|[CAtlMap::RemoveKey](../Topic/CAtlMap::RemoveKey.md)|요소를 제거 하려면이 메서드를 호출 하는 `CAtlMap` 키를 지정 된 개체를.|  
|[CAtlMap::SetAt](../Topic/CAtlMap::SetAt.md)|지도에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|  
|[CAtlMap::SetOptimalLoad](../Topic/CAtlMap::SetOptimalLoad.md)|최적의 로드를 설정 하려면이 메서드를 호출 하 여 `CAtlMap` 개체입니다.|  
|[CAtlMap::SetValueAt](../Topic/CAtlMap::SetValueAt.md)|지정 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 하는 `CAtlMap` 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAtlMap::operator](../Topic/CAtlMap::operator.md)|대체 하거나 새 요소에 추가 된 `CAtlMap`.|  
  
## 설명  
 `CAtlMap`핵심 요소 및 관련된 값의 배열 순서가 지정 되지 않은 관리 되는 특정된 형식, 매핑 배열을를 지원 합니다.  요소 \(키와 값으로 구성 된\) 많은 양의 데이터를 효율적으로 저장 하 고 검색할 수 있도록 하는 해싱 알고리즘을 사용 하 여 저장 됩니다.  
  
 `KTraits` 및 `VTraits` 매개 변수는 특성 클래스 요소를 옮기거나 복사 하는 데 필요한 추가 코드가 포함 되어 있습니다.  
  
 대신 `CAtlMap` 에서 제공 되는  [CRBMap](../../atl/reference/crbmap-class.md) 클래스.  `CRBMap`또한 키\/값 쌍을 저장 하지만 다른 성능 특성을 나타냅니다.  키를 항목을 삽입 하는 데 걸리는 시간을 확인 하거나 키를 삭제를 `CRBMap` 개체의 순서는  *log\(n\)*여기서  *n* 요소의 개수입니다.  에 대 한 `CAtlMap`, 최악의 시나리오의 순서 수 있지만 이러한 모든 작업 일반적으로 일정 한 시간 걸릴  *n*.  일반적인 경우에 따라서 `CAtlMap` 빠릅니다.  
  
 다른 차이 `CRBMap` 및 `CAtlMap` 저장된 요소 전체를 반복할 때 드러납니다.  에 `CRBMap`, 요소를 정렬 된 순서로 방문 합니다.  에 `CAtlMap`요소는 정렬 되 고 순서 없이 유추할 수 있습니다.  
  
 적은 수의 요소를 저장 해야 하는 경우 사용 하는 것은  [CSimpleMap](../../atl/reference/csimplemap-class.md) 대신 클래스.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Marquee 샘플](../../top/visual-cpp-samples.md)   
 [UpdatePV 샘플](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)