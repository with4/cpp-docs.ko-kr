---
title: "CComEnumImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComEnumImpl"
  - "ATL::CComEnumImpl"
  - "CComEnumImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumImpl class"
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComEnumImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 열거자 인터페이스 열거 되는 항목 배열에 저장 되는 위치에 대 한 구현을 제공 합니다.  
  
## 구문  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy  
>  
class ATL_NO_VTABLE CComEnumImpl :   
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
 동종의  [복사 정책 클래스](../../atl/atl-copy-policy-classes.md).  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComEnumImpl::CComEnumImpl](../Topic/CComEnumImpl::CComEnumImpl.md)|생성자입니다.|  
|[CComEnumImpl::~CComEnumImpl](../Topic/CComEnumImpl::~CComEnumImpl.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md)|구현 하는  [IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx).|  
|[CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)|열거자를 초기화합니다.|  
|[CComEnumImpl::Next](../Topic/CComEnumImpl::Next.md)|구현 하는  [IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](../Topic/CComEnumImpl::Reset.md)|구현 하는  [IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx).|  
|[CComEnumImpl::Skip](../Topic/CComEnumImpl::Skip.md)|구현 하는  [IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx).|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComEnumImpl::m\_begin](../Topic/CComEnumImpl::m_begin.md)|배열의 첫 번째 항목에 대 한 포인터입니다.|  
|[CComEnumImpl::m\_dwFlags](../Topic/CComEnumImpl::m_dwFlags.md)|복사를 통해 전달 되는 플래그 `Init`.|  
|[CComEnumImpl::m\_end](../Topic/CComEnumImpl::m_end.md)|배열의 마지막 항목 바로 뒤의 위치에 대 한 포인터입니다.|  
|[CComEnumImpl::m\_iter](../Topic/CComEnumImpl::m_iter.md)|배열에 있는 현재 항목에 대 한 포인터입니다.|  
|[CComEnumImpl::m\_spUnk](../Topic/CComEnumImpl::m_spUnk.md)|**IUnknown** 포인터의 개체를 열거 하 고 컬렉션을 제공 합니다.|  
  
## 설명  
 `CComEnumImpl`열거 되는 항목 배열에 저장 되는 위치는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다.  이 클래스와 유사 합니다의 `IEnumOnSTLImpl` 는 STL 컨테이너에서 열거자 인터페이스를 구현 하는 클래스를 기반으로 합니다.  
  
> [!NOTE]
>  자세한 차이점에 대 한 자세한 내용은 `CComEnumImpl` 및 `IEnumOnSTLImpl`를 참조 하십시오  [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md).  
  
 일반적으로 사용 됩니다  *하지* 이 인터페이스 구현에서 파생 하 여 사용자 고유의 열거자 클래스를 만들어야 합니다.  배열을 기반으로 하는 ATL에서 제공한 열거자를 사용 하려면 일반적인 인스턴스를 만들 수 있습니다  [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 그러나 사용자 지정 표시기 \(예를 들어, 하나는 열거자 인터페이스 외에 인터페이스를 노출\)를 제공 하려면이 클래스에서 파생 될 수 있습니다.  이 상황에서는 가능성이 무시 해야 되는  [CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md) 사용자 고유의 구현을 제공 하는 메서드.  
  
 자세한 내용은  [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md).  
  
## 상속 계층 구조  
 `Base`  
  
 `CComEnumImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum Class](../../atl/reference/ccomenum-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)