---
title: "CPrimitiveElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPrimitiveElementTraits<T>"
  - "CPrimitiveElementTraits"
  - "ATL.CPrimitiveElementTraits"
  - "ATL::CPrimitiveElementTraits<T>"
  - "ATL::CPrimitiveElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrimitiveElementTraits class"
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CPrimitiveElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 메서드를 제공 하는이 클래스와 함수에 대 한 컬렉션 클래스의 기본 데이터 형식을 구성 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename T  
> class CPrimitiveElementTraits :   
   public CDefaultElementTraits< T >  
```  
  
#### 매개 변수  
 `T`  
 컬렉션 클래스 개체에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CPrimitiveElementTraits::INARGTYPE](../Topic/CPrimitiveElementTraits::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[CPrimitiveElementTraits::OUTARGTYPE](../Topic/CPrimitiveElementTraits::OUTARGTYPE.md)|컬렉션 클래스 개체에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
## 설명  
 이 기본 정적 함수 및 이동, 복사, 비교, 및 컬렉션 클래스 개체에 저장 된 기본 데이터 형식 요소를 해시 하는 방법을 제공 합니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CPrimitiveElementTraits`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)