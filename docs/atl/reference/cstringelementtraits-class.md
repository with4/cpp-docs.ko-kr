---
title: "CStringElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CStringElementTraits<T>"
  - "ATL::CStringElementTraits<T>"
  - "CStringElementTraits"
  - "ATL.CStringElementTraits"
  - "ATL::CStringElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraits class"
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CStringElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 정적 함수를 사용 하 여 컬렉션 클래스를 저장 제공 `CString` 개체입니다.  
  
## 구문  
  
```  
  
      template<  
   typename T   
>  
class CStringElementTraits  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CStringElementTraits::INARGTYPE](../Topic/CStringElementTraits::INARGTYPE.md)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하는 데이터 형식입니다.|  
|[CStringElementTraits::OUTARGTYPE](../Topic/CStringElementTraits::OUTARGTYPE.md)|컬렉션 클래스 개체에서 요소를 검색 하는 데 사용 하는 데이터 형식입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStringElementTraits::CompareElements](../Topic/CStringElementTraits::CompareElements.md)|\(정적\) 문자열 두 요소가 같은지 비교 하려면이 함수를 호출 합니다.|  
|[CStringElementTraits::CompareElementsOrdered](../Topic/CStringElementTraits::CompareElementsOrdered.md)|\(정적\) 두 문자열 요소를 비교 하려면이 함수를 호출 합니다.|  
|[CStringElementTraits::CopyElements](../Topic/CStringElementTraits::CopyElements.md)|\(정적\) 복사 하려면이 함수를 호출 합니다. `CString` 요소 컬렉션 클래스 개체에 저장 합니다.|  
|[CStringElementTraits::Hash](../Topic/CStringElementTraits::Hash.md)|\(정적\) 지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 함수를 호출 합니다.|  
|[CStringElementTraits::RelocateElements](../Topic/CStringElementTraits::RelocateElements.md)|\(정적\) 위치를 변경 하려면이 함수를 호출 합니다. `CString` 요소 컬렉션 클래스 개체에 저장 합니다.|  
  
## 설명  
 이 클래스 복사, 이동 및 문자열을 비교 하 고 해시 값을 만드는 정적 함수를 제공 합니다.  이 함수는 컬렉션 클래스를 사용 하 여 문자열 기반 데이터를 저장할 때 유용 합니다.  사용  [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) 때 대\/소문자 구분 비교는 필수입니다.  사용  [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 문자열 개체 때 참조로 처리 될 수 있습니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** cstringt.h  
  
## 참고 항목  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI Class](../../atl/reference/cstringelementtraitsi-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)