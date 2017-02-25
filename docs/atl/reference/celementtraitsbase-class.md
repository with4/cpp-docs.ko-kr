---
title: "CElementTraitsBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CElementTraitsBase"
  - "ATL::CElementTraitsBase"
  - "ATL.CElementTraitsBase<T>"
  - "ATL::CElementTraitsBase<T>"
  - "ATL.CElementTraitsBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraitsBase class"
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CElementTraitsBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 기본 복사본을 제공 하며 메서드 컬렉션 클래스에 대 한 이동.  
  
## 구문  
  
```  
  
      template<  
   typename T  
>  
class CElementTraitsBase  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CElementTraitsBase::INARGTYPE](../Topic/CElementTraitsBase::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[CElementTraitsBase::OUTARGTYPE](../Topic/CElementTraitsBase::OUTARGTYPE.md)|컬렉션 클래스 개체에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CElementTraitsBase::CopyElements](../Topic/CElementTraitsBase::CopyElements.md)|컬렉션 클래스 개체에 저장 된 요소를 복사 하려면이 메서드를 호출 합니다.|  
|[CElementTraitsBase::RelocateElements](../Topic/CElementTraitsBase::RelocateElements.md)|컬렉션 클래스 개체에 저장 된 요소의 위치를 변경 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 이 기본 클래스 복사 및 재배치 요소 컬렉션 클래스의 메서드를 정의 합니다.  클래스에서 사용 되는  [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md),  [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), 및  [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)