---
title: "CDefaultElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDefaultElementTraits<T>"
  - "ATL.CDefaultElementTraits"
  - "ATL::CDefaultElementTraits"
  - "ATL.CDefaultElementTraits<T>"
  - "CDefaultElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultElementTraits class"
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CDefaultElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 기본 메서드 및 함수 컬렉션 클래스를 제공합니다.  
  
## 구문  
  
```  
  
      template<  
   typename T  
>  
class CDefaultElementTraits : public CElementTraitsBase< T >,  
   public CDefaultHashTraits< T >,  
   public CDefaultCompareTraits< T >  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## 설명  
 이 클래스 컬렉션 클래스 개체에 저장 된 해시 요소 및 이동, 복사, 비교, 기본 정적 함수와 메서드를 제공 합니다.  이 클래스의 함수 및 메서드를 파생 된  [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md),  [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), 및  [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md), 및 활용 하 여  [CElementTraits](../../atl/reference/celementtraits-class.md),  [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), 및  [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)