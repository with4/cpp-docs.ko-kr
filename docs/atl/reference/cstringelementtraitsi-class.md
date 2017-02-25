---
title: "CStringElementTraitsI Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStringElementTraitsI"
  - "CStringElementTraitsI"
  - "ATL.CStringElementTraitsI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraitsI class"
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStringElementTraitsI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 정적 함수 관련 컬렉션 클래스 개체에 저장 된 문자열을 제공 합니다.  유사 합니다  [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), 하지만 대\/소문자 구분 비교를 수행 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename T,  
   class CharTraits = CDefaultCharTraits< T::XCHAR >  
>  
class CStringElementTraitsI : public CElementTraitsBase< T >  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CStringElementTraitsI::INARGTYPE](../Topic/CStringElementTraitsI::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[CStringElementTraitsI::OUTARGTYPE](../Topic/CStringElementTraitsI::OUTARGTYPE.md)|컬렉션 클래스 개체에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStringElementTraitsI::CompareElements](../Topic/CStringElementTraitsI::CompareElements.md)|같은지, 대\/소문자를 무시 하 고 두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringElementTraitsI::CompareElementsOrdered](../Topic/CStringElementTraitsI::CompareElementsOrdered.md)|대\/소문자를 무시 하 고 두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringElementTraitsI::Hash](../Topic/CStringElementTraitsI::Hash.md)|지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.|  
  
## 설명  
 이 클래스는 문자열을 비교 하 고 해시 값을 만드는 정적 함수를 제공 합니다.  이 함수는 컬렉션 클래스를 사용 하 여 문자열 기반 데이터를 저장할 때 유용 합니다.  사용  [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 문자열 개체 때와 참조로 처리 될 수 있습니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CStringElementTraits Class](../../atl/reference/cstringelementtraits-class.md)