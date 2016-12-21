---
title: "CStringRefElementTraits Class | Microsoft Docs"
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
  - "CStringRefElementTraits"
  - "ATL.CStringRefElementTraits"
  - "ATL::CStringRefElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringRefElementTraits class"
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringRefElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 정적 함수 관련 컬렉션 클래스 개체에 저장 된 문자열을 제공 합니다.  문자열 개체 참조로 처리 됩니다.  
  
## 구문  
  
```  
  
      template<   
   typename T  
>  
class CStringRefElementTraits : public CElementTraitsBase< T >  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStringRefElementTraits::CompareElements](../Topic/CStringRefElementTraits::CompareElements.md)|문자열 두 요소가 같은지 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringRefElementTraits::CompareElementsOrdered](../Topic/CStringRefElementTraits::CompareElementsOrdered.md)|두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringRefElementTraits::Hash](../Topic/CStringRefElementTraits::Hash.md)|지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.|  
  
## 설명  
 이 클래스는 문자열을 비교 하 고 해시 값을 만드는 정적 함수를 제공 합니다.  이 함수는 컬렉션 클래스를 사용 하 여 문자열 기반 데이터를 저장할 때 유용 합니다.  달리  [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) 및  [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` 발생의 `CString` 로 전달 될 인수  **const CString &** 참조.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 상속 계층 구조  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)