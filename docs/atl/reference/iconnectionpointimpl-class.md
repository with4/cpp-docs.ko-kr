---
title: "IConnectionPointImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IConnectionPointImpl"
  - "IConnectionPointImpl"
  - "ATL::IConnectionPointImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연결 지점[C++], 구현"
  - "IConnectionPointImpl class"
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# IConnectionPointImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 연결 지점을 구현 합니다.  
  
## 구문  
  
```  
  
      template<  
   class T,  
   const IID* piid,  
   class CDV = CComDynamicUnkArray   
>  
class ATL_NO_VTABLE IConnectionPointImpl :  
   public _ICPLocator< piid >  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IConnectionPointImpl`.  
  
 `piid`  
 연결 지점 개체가 나타내는 인터페이스의 IID에 대 한 포인터입니다.  
  
 `CDV`  
 연결을 관리 하는 클래스입니다.  기본값은  [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), 무제한 연결을 허용 합니다.  또한 사용할 수 있습니다  [CComUnkArray](../../atl/reference/ccomunkarray-class.md), 고정 된 연결의 수를 지정 합니다.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IConnectionPointImpl::Advise](../Topic/IConnectionPointImpl::Advise.md)|연결 지점 및 싱크 간의 연결을 설정합니다.|  
|[IConnectionPointImpl::EnumConnections](../Topic/IConnectionPointImpl::EnumConnections.md)|연결 지점에 대 한 연결을 반복 하는 열거자를 만듭니다.|  
|[IConnectionPointImpl::GetConnectionInterface](../Topic/IConnectionPointImpl::GetConnectionInterface.md)|연결 지점에서 표시 되는 인터페이스의 IID를 가져옵니다.|  
|[IConnectionPointImpl::GetConnectionPointContainer](../Topic/IConnectionPointImpl::GetConnectionPointContainer.md)|연결 가능 개체에 대 한 인터페이스 포인터를 검색합니다.|  
|[IConnectionPointImpl::Unadvise](../Topic/IConnectionPointImpl::Unadvise.md)|통해 이전에 설정 된 연결을 종료 `Advise`.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[IConnectionPointImpl::m\_vec](../Topic/IConnectionPointImpl::m_vec.md)|연결 지점에 대 한 연결을 관리합니다.|  
  
## 설명  
 `IConnectionPointImpl`클라이언트로 송신 인터페이스를 노출 하는 개체를 허용 하는 연결 지점을 구현 합니다.  클라이언트는 싱크 라는 개체에서이 인터페이스를 구현 합니다.  
  
 ATL을 사용 하 여  [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) 연결 가능 개체를 구현 합니다.  각 연결 지점에 연결 가능 개체에 보내기 인터페이스를 식별 나타내는 `piid`.  클래스  *CDV* 는 연결 지점 및 싱크 간의 연결을 관리 합니다.  각 연결은 "쿠키 여." 고유 하 게 식별 됩니다.  
  
 ATL 연결 지점 사용에 대 한 자세한 내용은  [연결점](../../atl/atl-connection-points.md).  
  
## 상속 계층 구조  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Class Overview](../../atl/atl-class-overview.md)