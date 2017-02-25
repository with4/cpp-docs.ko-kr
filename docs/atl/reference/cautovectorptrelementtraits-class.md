---
title: "CAutoVectorPtrElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoVectorPtrElementTraits<T>"
  - "ATL.CAutoVectorPtrElementTraits"
  - "ATL.CAutoVectorPtrElementTraits<T>"
  - "ATL::CAutoVectorPtrElementTraits"
  - "CAutoVectorPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtrElementTraits class"
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAutoVectorPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 메서드, 정적 함수 및 형식 정의 새 벡터를 사용 하 여 스마트 포인터의 컬렉션을 만들고 연산자를 삭제 하면 편리 하 게 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
typename T  
>  
class CAutoVectorPtrElementTraits : public CDefaultElementTraits<  
ATL::CAutoVectorPtr< T>  
>  
```  
  
#### 매개 변수  
 `T`  
 포인터 형식입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](../Topic/CAutoVectorPtrElementTraits::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](../Topic/CAutoVectorPtrElementTraits::OUTARGTYPE.md)|컬렉션 클래스 개체에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
## 설명  
 이 클래스 대본이 스마트 포인터를 포함 하는 컬렉션 클래스 개체를 만들기 위한 메서드, 정적 함수 및 형식 정의 제공 합니다.  달리  [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md),이 클래스 사용 하 여 새 벡터 및 연산자를 삭제 합니다.  
  
## 상속 계층 구조  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [CAutoVectorPtr Class](../../atl/reference/cautovectorptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)