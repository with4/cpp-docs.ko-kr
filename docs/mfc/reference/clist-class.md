---
title: "CList Class | Microsoft Docs"
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
  - "CList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CList class"
  - "목록"
  - "목록, base class for"
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지원 목록에 액세스할 수 있는 고유 하지 않은 개체의 값으로 또는 순차적으로 정렬.  
  
## 구문  
  
```  
template< class TYPE, class ARG_TYPE = const TYPE& >   
class CList : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CList::CList](../Topic/CList::CList.md)|빈 순서가 지정 된 목록을 생성 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CList::AddHead](../Topic/CList::AddHead.md)|요소를 다른 목록에 있는 모든 요소는 \(새 머리 수\) 목록의 헤드에 추가 합니다.|  
|[CList::AddTail](../Topic/CList::AddTail.md)|요소를 다른 목록에 있는 모든 요소 \(새 꼬리 있습니다\) 목록 끝에 추가 합니다.|  
|[CList::Find](../Topic/CList::Find.md)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|  
|[CList::FindIndex](../Topic/CList::FindIndex.md)|인덱스에서 지정한 요소의 위치를 가져옵니다.|  
|[CList::GetAt](../Topic/CList::GetAt.md)|지정 된 위치에 있는 요소를 가져옵니다.|  
|[CList::GetCount](../Topic/CList::GetCount.md)|이 목록의 요소 수를 반환합니다.|  
|[CList::GetHead](../Topic/CList::GetHead.md)|Head 요소 목록 \(비어 있을 수 없습니다\)을 반환 합니다.|  
|[CList::GetHeadPosition](../Topic/CList::GetHeadPosition.md)|Head 요소 목록을 반환 합니다.|  
|[CList::GetNext](../Topic/CList::GetNext.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CList::GetPrev](../Topic/CList::GetPrev.md)|반복에 대 한 이전 요소를 가져옵니다.|  
|[CList::GetSize](../Topic/CList::GetSize.md)|이 목록의 요소 수를 반환합니다.|  
|[CList::GetTail](../Topic/CList::GetTail.md)|꼬리 요소 목록 \(비어 있을 수 없습니다\)을 반환 합니다.|  
|[CList::GetTailPosition](../Topic/CList::GetTailPosition.md)|목록의 꼬리 요소의 위치를 반환합니다.|  
|[CList::InsertAfter](../Topic/CList::InsertAfter.md)|지정 된 위치 뒤에 새 요소를 삽입합니다.|  
|[CList::InsertBefore](../Topic/CList::InsertBefore.md)|지정 된 위치 앞에 새 요소를 삽입합니다.|  
|[CList::IsEmpty](../Topic/CList::IsEmpty.md)|빈 목록 조건 \(요소\)에 대해 테스트 합니다.|  
|[CList::RemoveAll](../Topic/CList::RemoveAll.md)|이 목록에서 모든 요소를 제거합니다.|  
|[CList::RemoveAt](../Topic/CList::RemoveAt.md)|지정한 위치에 따라이 목록에서 요소를 제거 합니다.|  
|[CList::RemoveHead](../Topic/CList::RemoveHead.md)|머리의 목록에서 요소를 제거합니다.|  
|[CList::RemoveTail](../Topic/CList::RemoveTail.md)|목록의 꼬리에서 요소를 제거합니다.|  
|[CList::SetAt](../Topic/CList::SetAt.md)|지정 된 위치에 요소를 설정합니다.|  
  
#### 매개 변수  
 `TYPE`  
 목록에 저장 된 개체의 형식입니다.  
  
 `ARG` *\_* `TYPE`  
 목록에 저장 된 개체를 참조 하는 데 사용 되는 형식입니다.  참조 될 수 있습니다.  
  
## 설명  
 `CList`목록 이중 연결 목록 처럼 동작합니다.  
  
 형식의 변수에  **위치** 목록에 대 한 키입니다.  사용할 수 있는  **위치** 책갈피 위치를 저장 하 고 목록을 순서 대로 순회 하는 반복기 변수.  하지만 위치 인덱스와 동일 수 없습니다.  
  
 요소가 삽입 된 매우 빠른 목록 머리, 꼬리, 및 알려진  **위치**.  요소를 값 또는 인덱스로 조회 하려면 순차 검색을 필요 합니다.  이 검색 목록이 길면 오래 걸릴 수 있습니다.  
  
 목록에서 개별 요소를 덤프 해야 하는 경우 1 이상으로 깊이 덤프 컨텍스트를 설정 해야 합니다.  
  
 특정 멤버 함수 전역 도우미 함수는이 클래스 호출의 대부분의 사용에 대해 사용자 지정 해야 합니다의 `CList` 클래스입니다.  참조  [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md) "매크로 전역 변수" 섹션에서.  
  
 사용에 대 한 자세한 내용은 `CList`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 예제  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/CPP/clist-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## 요구 사항  
 **헤더:**  afxtempl.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)