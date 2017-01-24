---
title: "CMap Class | Microsoft Docs"
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
  - "CMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMap class"
  - "컬렉션 클래스, dictionary mapping"
  - "dictionary mapping class"
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고유 키 값에 매핑하는 사전 컬렉션 클래스입니다.  
  
## 구문  
  
```  
template< class KEY, class ARG_KEY, class VALUE, class ARG_VALUE >class CMap : public CObject  
```  
  
#### 매개 변수  
 `KEY`  
 지도 키로 사용 되는 개체의 클래스입니다.  
  
 `ARG` *\_* `KEY`  
 데이터 형식 사용 `KEY` 인수. 일반적으로 참조를 `KEY`.  
  
 `VALUE`  
 클래스 맵에 저장 된 개체입니다.  
  
 `ARG` *\_* `VALUE`  
 데이터 형식 사용 `VALUE` 인수. 일반적으로 참조를 `VALUE`.  
  
## Members  
  
### 공용 구조체  
  
|Name|설명|  
|----------|--------|  
|[CMap::CPair](../Topic/CMap::CPair.md)|키 값과 연결 된 개체의 값을 포함 하는 중첩 된 구조입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMap::CMap](../Topic/CMap::CMap.md)|키 값에 매핑되는 컬렉션을 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMap::GetCount](../Topic/CMap::GetCount.md)|이 지도에서 요소의 개수를 반환합니다.|  
|[CMap::GetHashTableSize](../Topic/CMap::GetHashTableSize.md)|해시 테이블에서 요소를 반환합니다.|  
|[CMap::GetNextAssoc](../Topic/CMap::GetNextAssoc.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CMap::GetSize](../Topic/CMap::GetSize.md)|이 지도에서 요소의 개수를 반환합니다.|  
|[CMap::GetStartPosition](../Topic/CMap::GetStartPosition.md)|첫 번째 요소를 반환합니다.|  
|[CMap::InitHashTable](../Topic/CMap::InitHashTable.md)|해시 테이블을 초기화 하 고 크기를 지정 합니다.|  
|[CMap::IsEmpty](../Topic/CMap::IsEmpty.md)|빈 지도 조건 \(요소\)에 대해 테스트 합니다.|  
|[CMap::Lookup](../Topic/CMap::Lookup.md)|지정 된 키에 매핑되는 값을 찾습니다.|  
|[CMap::PGetFirstAssoc](../Topic/CMap::PGetFirstAssoc.md)|첫 번째 요소에는 포인터를 반환합니다.|  
|[CMap::PGetNextAssoc](../Topic/CMap::PGetNextAssoc.md)|반복에 대 한 다음 요소에는 포인터를 가져옵니다.|  
|[CMap::PLookup](../Topic/CMap::PLookup.md)|키 값에 지정 된 값과 일치 하는 포인터를 반환 합니다.|  
|[CMap::RemoveAll](../Topic/CMap::RemoveAll.md)|이 지도에서 모든 요소를 제거합니다.|  
|[CMap::RemoveKey](../Topic/CMap::RemoveKey.md)|키에 지정 된 요소를 제거 합니다.|  
|[CMap::SetAt](../Topic/CMap::SetAt.md)|지도에 요소를 삽입합니다. 일치 하는 키가 없는 경우 기존 요소를 대체 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CMap::operator](../Topic/CMap::operator.md)|지도에 요소를 삽입 합니다.\-운영자 대체 `SetAt`.|  
  
## 설명  
 지도에 있는 키\-값 쌍 \(요소\)를 삽입 한 후 효율적으로 검색 하거나 삭제 키를 사용 하 여 액세스 하는 쌍 수 있습니다.  맵의 모든 요소를 반복할 수 있습니다.  
  
 형식의 변수에  **위치** 대체 액세스 항목에 사용 됩니다.  사용할 수 있는  **위치** 맵을 통해 반복 하 고 항목을 "기억" 할.  이 반복이 키 값으로 순차적입니다 생각 합니다. 그렇지 않습니다.  검색 된 요소의 시퀀스는 결정 되지 않았습니다.  
  
 특정 멤버 함수 전역 도우미 함수는이 클래스 호출의 대부분의 사용에 대해 사용자 지정 해야 합니다의 `CMap` 클래스입니다.  참조  [컬렉션 클래스에 대 한 읽기 권한만](../../mfc/reference/collection-class-helpers.md) 매크로 전역 변수 부분에 있는 `MFC``Reference`.  
  
 `CMap`우선 [CObject::Serialize](../Topic/CObject::Serialize.md) 의 요소를 덤프 및 serialization을 지원 합니다.  보관 사용 맵을 저장 하는 경우 `Serialize`, 각 지도 요소에 serialize 됩니다.  기본 구현 된 `SerializeElements` 도우미 함수는 비트 쓰기 하지.  파생 포인터 컬렉션 항목의 serialization에 대 한 정보에 대 한 `CObject` 또는 다른 사용자 정의 형식을 참조 하십시오. [방법: 형식이 안전한 컬렉션 만들기](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 지도 \(키 및 값\)의 개별 요소에 대 한 진단 덤프 해야 하는 경우 1 이상으로 깊이 덤프 컨텍스트를 설정 해야 합니다.  
  
 경우는 `CMap` 개체를 삭제 하거나 해당 요소를 제거할 경우 키 및 값 제거 됩니다.  
  
 맵 클래스 파생 목록 파생 비슷합니다.  문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md) 예는 특수 목록 클래스를 파생 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## 요구 사항  
 **헤더:**  afxtempl.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)