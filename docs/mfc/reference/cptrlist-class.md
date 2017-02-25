---
title: "CPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPtrList class"
  - "generic lists"
  - "목록, 제네릭"
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

void 포인터 목록을 지원합니다.  
  
## 구문  
  
```  
class CPtrList : public CObject  
```  
  
## Members  
 `CPtrList` 의 멤버함수는 [CObList](../../mfc/reference/coblist-class.md) 클래스의 멤버 함수와 유사합니다.  이 유사성 때문에  멤버 함수 사양에 대한  `CObList` 참조 설명서를 사용할 수 있습니다.  함수 매개 변수 또는 반환 값에 대한  `CObject`  포인터를 보는 모든 위치에서 포인터는  `void` 로 대체됩니다.  
  
 `CObject*& CObList::GetHead() const;`  
  
 예를 들어, 다음으로 변환됩니다.  
  
 `void*& CPtrList::GetHead() const;`  
  
## 설명  
 `CPtrList`은   `IMPLEMENT_DYNAMIC`  매크로를 통합하여 런타임 형식 액세스와  `CDumpContext`  개체에 덤핑하는 것을 지원합니다.  개별 포인터 목록 요소의 덤프가 필요하면, 덤프 컨텍스트 깊이는 1 이상으로 설정해야 합니다.  
  
 포인터가 목록은 serialize할 수 없습니다.  
  
 `CPtrList`  개체를 삭제하거나 요소가 제거될 경우, 참조는 엔티티 되지 않고 오로지 포인터만 제거됩니다.  
  
 `CPtrList` 사용에 대한 자세한 내용은 [Collections](../../mfc/collections.md)기사를 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## 요구 사항  
 **헤더:**  afxcoll.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)