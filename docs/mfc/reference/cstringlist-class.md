---
title: "CStringList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringList class"
  - "목록, string"
  - "문자열[C++], 컬렉션"
  - "문자열[C++], 목록"
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CStringList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

목록을 지 원하는 `CString` 개체입니다.  
  
## 구문  
  
```  
class CStringList : public CObject  
```  
  
## 멤버  
 멤버 함수를 `CStringList` 클래스의 멤버 함수와 유사  [CObList](../../mfc/reference/coblist-class.md).  이 유사성 때문에 사용할 수 있는 `CObList` 멤버 함수 사양에 대 한 설명서를 참조 합니다.  볼 위치는 `CObject` 포인터 반환 값으로 대체는 `CString` \(않습니다는 `CString` 포인터\).  볼 위치는 `CObject` 포인터가 함수 매개 변수로 대체는 `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 예를 들어, 변환  
  
 `CString& CStringList::GetHead() const;`  
  
 및  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 변환  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|빈 목록을 생성 합니다.|  
  
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
 모든 비교 문자 문자열에서 대신 문자열의 주소를 비교 하는 것을 의미 하는 값으로 이루어집니다.  
  
 `CStringList`통합 된 `IMPLEMENT_SERIAL` 매크로의 요소를 덤프 및 serialization을 지원 합니다.  목록을 경우 `CString` 개체 저장 보관, 연산자 오버 로드 된 삽입 하거나 사용 하는 `Serialize` 각 멤버 함수 `CString` 요소에 직렬화 할.  
  
 개별 덤프 해야 하는 경우 `CString` 요소를 설정 해야 심도 덤프 컨텍스트를 1 이상으로 합니다.  
  
 사용에 대 한 자세한 내용은 `CStringList`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)