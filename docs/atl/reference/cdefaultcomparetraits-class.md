---
title: "CDefaultCompareTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CDefaultCompareTraits<T>"
  - "ATL::CDefaultCompareTraits"
  - "ATL.CDefaultCompareTraits"
  - "ATL::CDefaultCompareTraits<T>"
  - "CDefaultCompareTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCompareTraits class"
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDefaultCompareTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 이와 같은 기본 요소 비교 기능을 제공합니다.  
  
## 구문  
  
```  
  
      template<  
   typename T  
>  
class CDefaultCompareTraits  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDefaultCompareTraits::CompareElements](../Topic/CDefaultCompareTraits::CompareElements.md)|\(정적\) 두 요소가 같은지 비교 하려면이 함수를 호출 합니다.|  
|[CDefaultCompareTraits::CompareElementsOrdered](../Topic/CDefaultCompareTraits::CompareElementsOrdered.md)|\(정적\) 크고 급 요소를 확인 하려면이 함수를 호출 합니다.|  
  
## 설명  
 이 클래스는 컬렉션 클래스 개체에 저장 되는 요소를 비교 하는 두 정적 함수를 포함 되어 있습니다.  이 클래스에서 활용 되는  [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md).  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)