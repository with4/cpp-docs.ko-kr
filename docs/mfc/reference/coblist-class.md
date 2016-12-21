---
title: "CObList Class | Microsoft Docs"
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
  - "CObList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObList class"
  - "목록, object"
  - "개체[C++], lists of"
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

고유 하지 않은 작업의 순서가 지정 된 지원 `CObject` 순차적으로 또는 포인터에 액세스할 수 있는 포인터 값입니다.  
  
## 구문  
  
```  
class CObList : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|에 대 한 빈 목록을 생성 `CObject` 포인터.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CObList::AddHead](../Topic/CObList::AddHead.md)|요소를 다른 목록에 있는 모든 요소는 \(새 머리 수\) 목록의 헤드에 추가 합니다.|  
|[CObList::AddTail](../Topic/CObList::AddTail.md)|요소를 다른 목록에 있는 모든 요소 \(새 꼬리 있습니다\) 목록 끝에 추가 합니다.|  
|[CObList::Find](../Topic/CObList::Find.md)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|  
|[CObList::FindIndex](../Topic/CObList::FindIndex.md)|인덱스에서 지정한 요소의 위치를 가져옵니다.|  
|[CObList::GetAt](../Topic/CObList::GetAt.md)|지정 된 위치에 있는 요소를 가져옵니다.|  
|[CObList::GetCount](../Topic/CObList::GetCount.md)|이 목록의 요소 수를 반환합니다.|  
|[CObList::GetHead](../Topic/CObList::GetHead.md)|Head 요소 목록 \(비어 있을 수 없습니다\)을 반환 합니다.|  
|[CObList::GetHeadPosition](../Topic/CObList::GetHeadPosition.md)|Head 요소 목록을 반환 합니다.|  
|[CObList::GetNext](../Topic/CObList::GetNext.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CObList::GetPrev](../Topic/CObList::GetPrev.md)|반복에 대 한 이전 요소를 가져옵니다.|  
|[CObList::GetSize](../Topic/CObList::GetSize.md)|이 목록의 요소 수를 반환합니다.|  
|[CObList::GetTail](../Topic/CObList::GetTail.md)|꼬리 요소 목록 \(비어 있을 수 없습니다\)을 반환 합니다.|  
|[CObList::GetTailPosition](../Topic/CObList::GetTailPosition.md)|목록의 꼬리 요소의 위치를 반환합니다.|  
|[CObList::InsertAfter](../Topic/CObList::InsertAfter.md)|지정 된 위치 뒤에 새 요소를 삽입합니다.|  
|[CObList::InsertBefore](../Topic/CObList::InsertBefore.md)|지정 된 위치 앞에 새 요소를 삽입합니다.|  
|[CObList::IsEmpty](../Topic/CObList::IsEmpty.md)|빈 목록 조건 \(요소\)에 대해 테스트 합니다.|  
|[CObList::RemoveAll](../Topic/CObList::RemoveAll.md)|이 목록에서 모든 요소를 제거합니다.|  
|[CObList::RemoveAt](../Topic/CObList::RemoveAt.md)|지정한 위치에 따라이 목록에서 요소를 제거 합니다.|  
|[CObList::RemoveHead](../Topic/CObList::RemoveHead.md)|머리의 목록에서 요소를 제거합니다.|  
|[CObList::RemoveTail](../Topic/CObList::RemoveTail.md)|목록의 꼬리에서 요소를 제거합니다.|  
|[CObList::SetAt](../Topic/CObList::SetAt.md)|지정 된 위치에 요소를 설정합니다.|  
  
## 설명  
 `CObList`목록 이중 연결 목록 처럼 동작합니다.  
  
 형식의 변수에  **위치** 목록에 대 한 키입니다.  사용할 수 있는  **위치** 목록 순서 대로 순회 하는 반복기 및 책갈피 위치를 저장할 변수.  하지만 위치 인덱스와 동일 수 없습니다.  
  
 요소가 삽입 된 매우 빠른 목록 머리, 꼬리, 및 알려진  **위치**.  요소를 값 또는 인덱스로 조회 하려면 순차 검색을 필요 합니다.  이 검색 목록이 길면 오래 걸릴 수 있습니다.  
  
 `CObList`통합 된 `IMPLEMENT_SERIAL` 매크로의 요소를 덤프 및 serialization을 지원 합니다.  목록을 경우 `CObject` 포인터 저장 보관, 연산자 오버 로드 된 삽입 하거나 사용 하는 `Serialize` 각 멤버 함수 `CObject` 요소에 직렬화 할.  
  
 개별 덤프 해야 하는 경우 `CObject` 목록에서 요소를 설정 해야 덤프 컨텍스트 깊이가 1 이상으로 합니다.  
  
 경우는 `CObList` 개체가 삭제 되거나 때 요소 제거만 `CObject` 포인터 제거, 오브젝트가 참조.  
  
 클래스에서 파생 될 수 있습니다 `CObList`.  새 목록 클래스에서 파생 된 개체 포인터를 보유 하도록 설계, `CObject`, 새 데이터 멤버와 새 멤버 함수를 추가 합니다.  삽입 중 하나를 수 있기 때문에 결과 목록이 엄격 하 게 형식이 안전 아닙니다 `CObject` 포인터.  
  
> [!NOTE]
>  사용 해야는  [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) 매크로 목록을 serialize 하려는 경우 파생된 클래스의 구현에서입니다.  
  
 사용에 대 한 자세한 내용은 `CObList`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStringList Class](../../mfc/reference/cstringlist-class.md)   
 [CPtrList Class](../../mfc/reference/cptrlist-class.md)