---
title: "CRBTree Class | Microsoft Docs"
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
  - "ATL.CRBTree"
  - "CRBTree"
  - "ATL::CRBTree"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBTree class"
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBTree Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 만들고 빨강\-검정 트리를 사용 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBTree  
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
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CRBTree::KINARGTYPE](../Topic/CRBTree::KINARGTYPE.md)|키 입력된 인수로 전달 될 때 사용 되는 형식입니다.|  
|[CRBTree::KOUTARGTYPE](../Topic/CRBTree::KOUTARGTYPE.md)|키를 출력 인수로 반환 될 때 사용 되는 형식입니다.|  
|[CRBTree::VINARGTYPE](../Topic/CRBTree::VINARGTYPE.md)|값을 입력된 인수로 전달 될 때 사용 되는 형식입니다.|  
|[CRBTree::VOUTARGTYPE](../Topic/CRBTree::VOUTARGTYPE.md)|값 출력 인수로 전달 될 때 사용 되는 형식입니다.|  
  
### 공용 클래스  
  
|Name|설명|  
|----------|--------|  
|[CRBTree::CPair Class](../Topic/CRBTree::CPair%20Class.md)|키 \/ 값 요소를 포함 하는 클래스입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRBTree::~CRBTree](../Topic/CRBTree::~CRBTree.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRBTree::FindFirstKeyAfter](../Topic/CRBTree::FindFirstKeyAfter.md)|다음 사용 가능한 키를 사용 하 여 요소의 위치를 찾기 위해이 메서드를 호출 합니다.|  
|[CRBTree::GetAt](../Topic/CRBTree::GetAt.md)|트리의 지정 된 위치에 요소를 가져오고이 메서드를 호출 합니다.|  
|[CRBTree::GetCount](../Topic/CRBTree::GetCount.md)|요소 트리를 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)|트리 헤드에 있는 요소의 위치 값을 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetKeyAt](../Topic/CRBTree::GetKeyAt.md)|키 트리의 지정 된 위치에서 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)|저장 요소에 대 한 포인터를 가져오려면이 메서드를 호출 하는 `CRBTree` 개체 및 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetNextAssoc](../Topic/CRBTree::GetNextAssoc.md)|키 \/ 값 맵에 저장 요소를 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetNextKey](../Topic/CRBTree::GetNextKey.md)|키 요소를 트리에 저장 하려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)|요소를 트리에 저장 값을 가져오는 데이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|  
|[CRBTree::GetPrev](../Topic/CRBTree::GetPrev.md)|저장 된 요소에 대 한 포인터를 가져오려면이 메서드를 호출 하는 `CRBTree` 개체를 가리킨 다음 이전 요소를 위치를 업데이트 합니다.|  
|[CRBTree::GetTailPosition](../Topic/CRBTree::GetTailPosition.md)|요소 트리의 꼬리의 위치 값을 가져오려면이 메서드를 호출 합니다.|  
|[CRBTree::GetValueAt](../Topic/CRBTree::GetValueAt.md)|지정 된 위치에 저장 된 값을 검색 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.|  
|[CRBTree::IsEmpty](../Topic/CRBTree::IsEmpty.md)|빈 트리 객체를 테스트 하려면이 메서드를 호출 합니다.|  
|[CRBTree::RemoveAll](../Topic/CRBTree::RemoveAll.md)|모든 요소를 제거 하려면이 메서드를 호출 하 여  **CRBTree**  개체입니다.|  
|[CRBTree::RemoveAt](../Topic/CRBTree::RemoveAt.md)|지정 된 위치에서 요소를 제거 하려면이 메서드를 호출 하는  **CRBTree**  개체.|  
|[CRBTree::SetValueAt](../Topic/CRBTree::SetValueAt.md)|지정 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 하는 `CRBTree` 개체입니다.|  
  
## 설명  
 빨강\-검정 트리 추가 사용 하 여 이진 검색 트리입니다이 되지 않도록 노드 당 정보 비트 "균형,"는, 트리의 높이 불균형적 커지지 않고 성능에 영향을.  
  
 이 템플릿 클래스에서 사용 하도록 설계 되었습니다  [CRBMap](../../atl/reference/crbmap-class.md) 및  [CRBMultiMap](../../atl/reference/crbmultimap-class.md).  대량 이러한 파생된 클래스를 만드는 방법으로 제공 됩니다 `CRBTree`.  
  
 컬렉션 클래스는 다양 한 기능 및 성능 특성에 대 한 자세한 설명은 참조 하십시오  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)