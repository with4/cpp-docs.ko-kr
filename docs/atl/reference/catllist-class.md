---
title: "CAtlList Class | Microsoft Docs"
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
  - "ATL.CAtlList"
  - "CAtlList"
  - "ATL::CAtlList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlList class"
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 만들고 관리 하는 목록 개체 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename E,  
   class ETraits = CElementTraits< E >  
>  
class CAtlList  
```  
  
#### 매개 변수  
 `E`  
 요소 형식입니다.  
  
 `ETraits`  
 복사 또는 이동 요소를 사용 하는 코드입니다.  참조  [CElementTraits 클래스](../../atl/reference/celementtraits-class.md) 에 대 한 자세한 내용은.  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CAtlList::INARGTYPE](../Topic/CAtlList::INARGTYPE.md)||  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAtlList::CAtlList](../Topic/CAtlList::CAtlList.md)|생성자입니다.|  
|[CAtlList::~CAtlList](../Topic/CAtlList::~CAtlList.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAtlList::AddHead](../Topic/CAtlList::AddHead.md)|목록의 헤드에 요소를 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AddHeadList](../Topic/CAtlList::AddHeadList.md)|기존 목록 목록의 헤드에 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AddTail](../Topic/CAtlList::AddTail.md)|이 목록 끝에 요소를 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AddTailList](../Topic/CAtlList::AddTailList.md)|기존 목록이이 목록 끝에 추가 하려면이 메서드를 호출 합니다.|  
|[CAtlList::AssertValid](../Topic/CAtlList::AssertValid.md)|목록에서 사용할 수 있는지 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlList::Find](../Topic/CAtlList::Find.md)|목록에 지정 된 요소를 검색 하려면이 메서드를 호출 합니다.|  
|[CAtlList::FindIndex](../Topic/CAtlList::FindIndex.md)|인덱스 값이 지정 된 요소의 위치를 얻으려면이 메서드를 호출 합니다.|  
|[CAtlList::GetAt](../Topic/CAtlList::GetAt.md)|목록에서 지정한 위치에 있는 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetCount](../Topic/CAtlList::GetCount.md)|목록에서 개체를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetHead](../Topic/CAtlList::GetHead.md)|머리의 목록에 있는 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetHeadPosition](../Topic/CAtlList::GetHeadPosition.md)|목록의 헤드의 위치를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlList::GetNext](../Topic/CAtlList::GetNext.md)|목록에서 다음 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetPrev](../Topic/CAtlList::GetPrev.md)|목록에서 이전 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetTail](../Topic/CAtlList::GetTail.md)|목록의 끝에 있는 요소를 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlList::GetTailPosition](../Topic/CAtlList::GetTailPosition.md)|목록의 끝의 위치를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlList::InsertAfter](../Topic/CAtlList::InsertAfter.md)|지정 된 위치 다음 목록에 새 요소를 삽입 하려면이 메서드를 호출 합니다.|  
|[CAtlList::InsertBefore](../Topic/CAtlList::InsertBefore.md)|목록에서 지정한 위치 앞에 새 요소를 삽입 하려면이 메서드를 호출 합니다.|  
|[CAtlList::IsEmpty](../Topic/CAtlList::IsEmpty.md)|목록이 비어 있는 경우 확인 하려면이 메서드를 호출 합니다.|  
|[CAtlList::MoveToHead](../Topic/CAtlList::MoveToHead.md)|머리의 목록에 지정 된 요소를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlList::MoveToTail](../Topic/CAtlList::MoveToTail.md)|목록의 끝에 지정 된 요소를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveAll](../Topic/CAtlList::RemoveAll.md)|목록에서 모든 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveAt](../Topic/CAtlList::RemoveAt.md)|목록에서 단일 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveHead](../Topic/CAtlList::RemoveHead.md)|머리의 목록에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveHeadNoReturn](../Topic/CAtlList::RemoveHeadNoReturn.md)|값을 반환 하지 않고 머리의 목록에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveTail](../Topic/CAtlList::RemoveTail.md)|목록의 끝에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::RemoveTailNoReturn](../Topic/CAtlList::RemoveTailNoReturn.md)|값을 반환 하지 않고 목록의 끝에 있는 요소를 제거 하려면이 메서드를 호출 합니다.|  
|[CAtlList::SetAt](../Topic/CAtlList::SetAt.md)|목록의 지정 된 위치는 요소의 값을 설정 하려면이 메서드를 호출 합니다.|  
|[CAtlList::SwapElements](../Topic/CAtlList::SwapElements.md)|목록에서에서 요소를 교체 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 `CAtlList` 클래스 지원 순차적으로 또는 값으로 액세스할 수 있는 고유 하지 않은 개체 목록을 정렬 합니다.  `CAtlList`목록 이중 연결된 목록 처럼 동작합니다.  각 목록에는 머리와 꼬리를 포함 하 고 새 요소 \(또는 경우에 따라 목록\) 두 목록의 끝에 추가 하거나 특정 요소를 전후에 삽입 수 있습니다.  
  
 대부분의 `CAtlList` 메서드 확인 위치 값을 사용 합니다.  이 값이 위치 요소 저장 되 고 해야 없습니다 계산 하거나 직접 예측 하는 실제 메모리 위치를 참조 하는 방법으로 사용 됩니다.  에 액세스 해야 하는 경우는  *n*th 요소는 메서드 목록에서  [CAtlList::FindIndex](../Topic/CAtlList::FindIndex.md) 는 지정 된 인덱스에 대 한 해당 위치 값을 반환 합니다.  메서드  [CAtlList::GetNext](../Topic/CAtlList::GetNext.md) 및  [CAtlList::GetPrev](../Topic/CAtlList::GetPrev.md) 개체 목록에서 반복 하는 데 있습니다.  
  
 ATL을 사용할 수 있는 컬렉션 클래스에 대 한 자세한 내용은 참조 하십시오.  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CList Class](../../mfc/reference/clist-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)