---
title: "IServiceProviderImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl"
  - "ATL::IServiceProviderImpl"
  - "IServiceProviderImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IServiceProvider 인터페이스, ATL 구현"
  - "IServiceProviderImpl class"
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IServiceProviderImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 기본 구현 된 `IServiceProvider` 인터페이스.  
  
## 구문  
  
```  
  
      template <  
   class T  
>   
class ATL_NO_VTABLE IServiceProviderImpl :  
   public IServiceProvider  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IServiceProviderImpl`.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IServiceProviderImpl::QueryService](../Topic/IServiceProviderImpl::QueryService.md)|또는 지정 된 서비스에 액세스 하 고 서비스에 대해 지정 된 인터페이스에 인터페이스 포인터를 반환 합니다.|  
  
## 설명  
 `IServiceProvider` 인터페이스 GUID에 의해 지정 된 서비스를 찾고 서비스에서 요청한 인터페이스에 대 한 인터페이스 포인터를 반환 합니다.  클래스 `IServiceProviderImpl` 는이 인터페이스의 기본 구현을 제공 합니다.  
  
 **IServiceProviderImpl**  메서드가 지정:  [QueryService](../Topic/IServiceProviderImpl::QueryService.md), 만듭니다 또는 지정 된 서비스에 액세스 하 고 지정 된 인터페이스는 서비스에 대 한 인터페이스 포인터를 반환 합니다.  
  
 `IServiceProviderImpl`시작 서비스 맵을 사용 하 여  [BEGIN\_SERVICE\_MAP](../Topic/BEGIN_SERVICE_MAP.md) 하 고 끝나는  [END\_SERVICE\_MAP](../Topic/END_SERVICE_MAP.md).  
  
 서비스 맵 항목이 두 개 포함 되어 있습니다:  [SERVICE\_ENTRY](../Topic/SERVICE_ENTRY.md), 지원 개체에 의해 지정 된 서비스 id \(SID\)를 나타내는 및  [SERVICE\_ENTRY\_CHAIN](../Topic/SERVICE_ENTRY_CHAIN.md), 호출 `QueryService` 다른 개체 체인에.  
  
## 상속 계층 구조  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)