---
title: "CHeapPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CHeapPtrList"
  - "CHeapPtrList"
  - "ATL.CHeapPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrList class"
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHeapPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 힙 포인터 목록을 구성할 때 유용한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
typename E,  
class Allocator = ATL::CCRTAllocator  
>  
class CHeapPtrList : public CAtlList<  
ATL::CHeapPtr< E, Allocator>,  
CHeapPtrElementTraits< E, Allocator>  
>  
```  
  
#### 매개 변수  
 `E`  
 컬렉션 클래스에 저장 하는 개체 형식입니다.  
  
 `Allocator`  
 사용 하는 메모리 할당 클래스입니다.  기본값은  [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHeapPtrList::CHeapPtrList](../Topic/CHeapPtrList::CHeapPtrList.md)|생성자입니다.|  
  
## 설명  
 이 클래스는 생성자를 제공 및 파생 메서드를  [CAtlList](../../atl/reference/catllist-class.md) 및  [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) 힙 포인터를 저장 하는 컬렉션 클래스 개체 만들기를 지원 합니다.  
  
## 상속 계층 구조  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CAtlList Class](../../atl/reference/catllist-class.md)   
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits Class](../../atl/reference/cheapptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)