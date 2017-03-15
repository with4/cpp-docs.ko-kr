---
title: "ICollectionOnSTLImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.ICollectionOnSTLImpl"
  - "ATL::ICollectionOnSTLImpl"
  - "ICollectionOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl class"
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# ICollectionOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 컬렉션 클래스를 사용 하는 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template <  
   class T,  
   class CollType,  
   class ItemType,  
   class CopyItem,  
   class EnumType  
>  
class ICollectionOnSTLImpl :  
   public T  
```  
  
#### 매개 변수  
 `T`  
 COM 컬렉션 인터페이스입니다.  
  
 `CollType`  
 STL 컨테이너 클래스입니다.  
  
 *ItemType*  
 컨테이너 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 *CopyItem*  
 A  [복사 정책 클래스](../../atl/atl-copy-policy-classes.md).  
  
 *EnumType*  
 A  [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)\-호환 열거자 클래스.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ICollectionOnSTLImpl::get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md)|컬렉션에 대 한 열거자 개체를 반환합니다.|  
|[ICollectionOnSTLImpl::get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md)|컬렉션에서 요소의 개수를 반환합니다.|  
|[ICollectionOnSTLImpl::get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md)|요청 된 항목을 컬렉션에서 반환합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[ICollectionOnSTLImpl::m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md)|컬렉션입니다.|  
  
## 설명  
 이 클래스는 컬렉션 인터페이스의 세 가지 방법에 대 한 구현을 제공 합니다.  [get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md),  [get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md), 및  [get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md).  
  
 이 클래스를 사용.  
  
-   정의 하거나 빌릴 컬렉션 인터페이스를 구현 합니다.  
  
-   클래스의 특수화에서 파생 될 `ICollectionOnSTLImpl` 이 컬렉션 인터페이스를 기반으로 합니다.  
  
-   처리지 않습니다 컬렉션 인터페이스에서 메서드를 구현 하 여 파생된 클래스를 사용 `ICollectionOnSTLImpl`.  
  
> [!NOTE]
>  이중 인터페이스는 컬렉션 인터페이스의 경우 클래스에서 파생 될  [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), passing는 `ICollectionOnSTLImpl` 특수화로 ATL의 구현을 제공 하려면 첫 번째 템플릿 매개 변수는 `IDispatch` 메서드.  
  
-   항목에 추가 된  [m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md) 컬렉션을 채우려면 구성원.  
  
 자세한 내용 및 예제를 참조 하십시오.  [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md).  
  
## 상속 계층 구조  
 `T`  
  
 `ICollectionOnSTLImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [ATLCollections 샘플](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)