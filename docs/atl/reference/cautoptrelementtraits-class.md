---
title: "CAutoPtrElementTraits Class | Microsoft Docs"
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
  - "ATL.CAutoPtrElementTraits"
  - "CAutoPtrElementTraits"
  - "ATL::CAutoPtrElementTraits<T>"
  - "ATL.CAutoPtrElementTraits<T>"
  - "ATL::CAutoPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrElementTraits class"
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스마트 포인터의 컬렉션을 만들 때 메서드, 정적 함수 및 형식 정의 유용 하 게이 클래스를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
typename T  
>  
class CAutoPtrElementTraits : public CDefaultElementTraits<  
ATL::CAutoPtr< T>  
>  
```  
  
#### 매개 변수  
 `T`  
 포인터 형식입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CAutoPtrElementTraits::INARGTYPE](../Topic/CAutoPtrElementTraits::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[CAutoPtrElementTraits::OUTARGTYPE](../Topic/CAutoPtrElementTraits::OUTARGTYPE.md)|컬렉션 클래스 개체에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
## 설명  
 이 클래스 대본이 스마트 포인터를 포함 하는 컬렉션 클래스 개체를 만들기 위한 메서드, 정적 함수 및 형식 정의 제공 합니다.  클래스는  [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 및  [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 파생 `CAutoPtrElementTraits`.  새 벡터 및 delete 연산자 스마트 포인터의 컬렉션을 구축 해야 하는 경우 사용  [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 대신 합니다.  
  
## 상속 계층 구조  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)