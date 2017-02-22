---
title: "CTypedPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTypedPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrList class"
  - "linked lists [C++]"
  - "lists [C++]"
  - "pointer lists"
  - "template classes, CTypedPtrList class"
  - "type-safe collections"
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CTypedPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 안전 "래퍼" 클래스의 개체에 대 한 제공 `CPtrList`.  
  
## 구문  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### 매개 변수  
 `BASE_CLASS`  
 형식화 된 포인터 목록 클래스의 기본 클래스입니다. 포인터가 목록 클래스 여야 합니다 \(`CObList` 또는 `CPtrList`\).  
  
 `TYPE`  
 기본 클래스 목록에 저장 된 요소의 형식입니다.  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTypedPtrList::AddHead](../Topic/CTypedPtrList::AddHead.md)|요소를 다른 목록에 있는 모든 요소는 \(새 머리 수\) 목록의 헤드에 추가 합니다.|  
|[CTypedPtrList::AddTail](../Topic/CTypedPtrList::AddTail.md)|요소를 다른 목록에 있는 모든 요소 \(새 꼬리 있습니다\) 목록 끝에 추가 합니다.|  
|[CTypedPtrList::GetAt](../Topic/CTypedPtrList::GetAt.md)|지정 된 위치에 있는 요소를 가져옵니다.|  
|[CTypedPtrList::GetHead](../Topic/CTypedPtrList::GetHead.md)|Head 요소 목록 \(비어 있을 수 없습니다\)을 반환 합니다.|  
|[CTypedPtrList::GetNext](../Topic/CTypedPtrList::GetNext.md)|반복에 대 한 다음 요소를 가져옵니다.|  
|[CTypedPtrList::GetPrev](../Topic/CTypedPtrList::GetPrev.md)|반복에 대 한 이전 요소를 가져옵니다.|  
|[CTypedPtrList::GetTail](../Topic/CTypedPtrList::GetTail.md)|꼬리 요소 목록 \(비어 있을 수 없습니다\)을 반환 합니다.|  
|[CTypedPtrList::RemoveHead](../Topic/CTypedPtrList::RemoveHead.md)|머리의 목록에서 요소를 제거합니다.|  
|[CTypedPtrList::RemoveTail](../Topic/CTypedPtrList::RemoveTail.md)|목록의 꼬리에서 요소를 제거합니다.|  
|[CTypedPtrList::SetAt](../Topic/CTypedPtrList::SetAt.md)|지정 된 위치에 요소를 설정합니다.|  
  
## 설명  
 사용 하는 경우 `CTypedPtrList` 대신 `CObList` 또는 `CPtrList`, 형식 검사를 C\+\+ 기능이 일치 하지 않는 포인터 형식에 의해 발생 하는 오류를 제거 하는 데 도움이 됩니다.  
  
 또한는 `CTypedPtrList` 래퍼를 사용한 경우 해야 하는 캐스팅에 많은 수행 `CObList` 또는 `CPtrList`.  
  
 때문에 모든 `CTypedPtrList` 함수는 인라인, 사용이 크게 미치지 않습니다 크기나 코드 속도.  
  
 목록에서 파생 `CObList` 에서 파생 된 있지만 serialize 될 `CPtrList` 수 없습니다.  
  
 경우는 `CTypedPtrList` 개체를 삭제 하거나 해당 요소를 제거할 경우의 포인터만 제거 되 고 엔터티 참조는 없습니다.  
  
 사용에 대 한 자세한 내용은 `CTypedPtrList`, 문서를 참조 하십시오.  [컬렉션](../../mfc/collections.md) 및  [템플릿 기반 클래스](../../mfc/template-based-classes.md).  
  
## 예제  
 인스턴스를 만드는이 예제 `CTypedPtrList`, 개체 추가, 목록 디스크에 serialize 및 해당 개체를 삭제 합니다.  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/CPP/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/CPP/ctypedptrlist-class_2.cpp)]  
  
## 상속 계층 구조  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## 요구 사항  
 **헤더:**  afxtempl.h  
  
## 참고 항목  
 [MFC 샘플 수집](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPtrList Class](../../mfc/reference/cptrlist-class.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)