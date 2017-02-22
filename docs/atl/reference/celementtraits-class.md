---
title: "CElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CElementTraits<T>"
  - "ATL::CElementTraits"
  - "ATL.CElementTraits"
  - "ATL::CElementTraits<T>"
  - "CElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraits class"
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 이동, 복사, 비교 및 해시 작업에 대 한 메서드 및 함수를 제공 합니다 컬렉션 클래스로 사용 됩니다.  
  
## 구문  
  
```  
  
      template<  
   typename T  
>  
class CElementTraits : public CDefaultElementTraits< T >  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## 설명  
 이 클래스 컬렉션 클래스 개체에 저장 된 해시 요소 및 이동, 복사, 비교, 기본 정적 함수와 메서드를 제공 합니다.  `CElementTraits`이러한 작업의 기본 공급자로 컬렉션 클래스에 의해 지정 된  [CAtlArray](../../atl/reference/catlarray-class.md),  [CAtlList](../../atl/reference/catllist-class.md),  [CRBMap](../../atl/reference/crbmap-class.md),  [CRBMultiMap](../../atl/reference/crbmultimap-class.md), 및  [CRBTree](../../atl/reference/crbtree-class.md).  
  
 단순 데이터 형식에 대 한 기본 구현에서 사용할 수 있지만 메서드와 함수 보다 복잡 한 개체를 저장 하는 컬렉션 클래스를 사용 하는 경우 사용자 지정 구현으로 재정의 해야 합니다.  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)