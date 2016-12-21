---
title: "IEnumOnSTLImpl Class | Microsoft Docs"
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
  - "IEnumOnSTLImpl"
  - "ATL.IEnumOnSTLImpl"
  - "ATL::IEnumOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IEnumOnSTLImpl class"
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IEnumOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

열거자 인터페이스는 STL 컬렉션에 따라이 클래스를 정의 합니다.  
  
## 구문  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType  
>  
class ATL_NO_VTABLE IEnumOnSTLImpl :  
   public Base  
```  
  
#### 매개 변수  
 `Base`  
 COM 열거자 \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\) 인터페이스.  
  
 `piid`  
 열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 `T`  
 열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 `Copy`  
 A  [복사 정책 클래스](../../atl/atl-copy-policy-classes.md).  
  
 `CollType`  
 STL 컨테이너 클래스입니다.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IEnumOnSTLImpl::Clone](../Topic/IEnumOnSTLImpl::Clone.md)|구현 하는  [IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx).|  
|[IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md)|열거자를 초기화합니다.|  
|[IEnumOnSTLImpl::Next](../Topic/IEnumOnSTLImpl::Next.md)|구현 하는  [IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx).|  
|[IEnumOnSTLImpl::Reset](../Topic/IEnumOnSTLImpl::Reset.md)|구현 하는  [IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx).|  
|[IEnumOnSTLImpl::Skip](../Topic/IEnumOnSTLImpl::Skip.md)|구현 하는  [IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx).|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[IEnumOnSTLImpl::m\_iter](../Topic/IEnumOnSTLImpl::m_iter.md)|컬렉션에서 열거자의 현재 위치를 나타내는 반복기입니다.|  
|[IEnumOnSTLImpl::m\_pcollection](../Topic/IEnumOnSTLImpl::m_pcollection.md)|열거할 항목 보유 STL 컨테이너에 대 한 포인터입니다.|  
|[IEnumOnSTLImpl::m\_spUnk](../Topic/IEnumOnSTLImpl::m_spUnk.md)|**IUnknown** 포인터를 개체의 컬렉션을 제공 합니다.|  
  
## 설명  
 `IEnumOnSTLImpl`열거 되는 항목은 호환 STL 컨테이너에 저장 되는 위치는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다.  이 클래스와 유사 합니다의  [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) 배열에서 열거자 인터페이스에 대 한 구현을 제공 하는 클래스를 기반으로 합니다.  
  
> [!NOTE]
>  참조  [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) 자세한 차이점에 대 한 자세한 내용은 `CComEnumImpl` 및 `IEnumOnSTLImpl`.  
  
 일반적으로 사용 됩니다  *하지* 이 인터페이스 구현에서 파생 하 여 사용자 고유의 열거자 클래스를 만들어야 합니다.  ATL에서 제공한 열거자는 STL 컨테이너에서 기준으로 사용 하려는 경우 일반적인 인스턴스를 만들 수 있습니다  [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)에서 파생 하는 열거자를 반환 하는 컬렉션 클래스를 만들 수  [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 그러나 사용자 지정 표시기 \(예를 들어, 하나는 열거자 인터페이스 외에 인터페이스를 노출\)를 제공 하려면이 클래스에서 파생 될 수 있습니다.  이 상황에서 재정의 해야 하는 것입니다는  [복제](../Topic/IEnumOnSTLImpl::Clone.md) 메서드 자체 구현을 제공 합니다.  
  
## 상속 계층 구조  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)