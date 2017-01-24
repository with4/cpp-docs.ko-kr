---
title: "IDispatchImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispatchImpl"
  - "ATL.IDispatchImpl"
  - "ATL::IDispatchImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이중 인터페이스, 클래스"
  - "ATL에서의 IDispatch 클래스 지원"
  - "IDispatchImpl 클래스"
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispatchImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 구현을 제공 된 `IDispatch` 이중 인터페이스의 일부로.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
template<  
   class T,  
   const IID* piid= &__uuidof(T),  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>   
class ATL_NO_VTABLE IDispatchImpl :  
   public T  
```  
  
#### 매개 변수  
 \[in\] `T`  
 이중 인터페이스입니다.  
  
 \[in\] `piid`  
 IID에 대 한 포인터 `T`.  
  
 \[in\] `plibid`  
 LIBID 인터페이스에 대 한 정보를 포함 하는 형식 라이브러리에 대 한 포인터입니다.  기본적으로 서버 형식 라이브러리에 전달 됩니다.  
  
 \[in\] `wMajor`  
 형식 라이브러리의 주 버전입니다.  기본적으로 값은 1입니다.  
  
 \[in\] `wMinor`  
 형식 라이브러리의 부 버전입니다.  기본적으로 값은 0입니다.  
  
 \[in\] `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`.  기본값은 `CComTypeInfoHolder`입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[IDispatchImpl::IDispatchImpl](../Topic/IDispatchImpl::IDispatchImpl.md)|생성자입니다.  호출 `AddRef` 에서 이중 인터페이스의 형식 정보를 관리 하는 보호 된 멤버 변수.  소멸자가 호출 `Release`.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IDispatchImpl::GetIDsOfNames](../Topic/IDispatchImpl::GetIDsOfNames.md)|이름 집합을 해당하는 디스패치 식별자 집합에 매핑합니다.|  
|[IDispatchImpl::GetTypeInfo](../Topic/IDispatchImpl::GetTypeInfo.md)|이중 인터페이스의 형식 정보를 검색합니다.|  
|[IDispatchImpl::GetTypeInfoCount](../Topic/IDispatchImpl::GetTypeInfoCount.md)|이중 인터페이스를 사용할 수 있는 형식 정보가 있는지 확인 합니다.|  
|[IDispatchImpl::Invoke](../Topic/IDispatchImpl::Invoke.md)|이중 인터페이스에서 노출 하는 속성 및 메서드 액세스를 제공 합니다.|  
  
## 설명  
 `IDispatchImpl`기본 구현을 제공 된 `IDispatch` 의 모든 개체에서 이중 인터페이스.  이중 인터페이스에서 파생 된 `IDispatch` 및 자동화 호환 형식에만 사용 합니다.  Dispinterface 같은 초기 바인딩 및 런타임에 바인딩 이중 인터페이스를 지원합니다. 그러나 이중 인터페이스는 vtable 바인딩을 지 원합니다.  
  
 다음 예제에서는 `IDispatchImpl`를 구현하는 일반적인 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/CPP/idispatchimpl-class_1.h)]  
  
 기본적으로 `IDispatchImpl` 클래스에 대 한 형식 정보 조회 `T` 레지스트리에서.  사용 하 여 등록 되지 않은 인터페이스는 `IDispatchImpl` 클래스는 미리 정의 된 버전 번호를 사용 하 여 레지스트리를 액세스 하지 않고.  만들 경우는 `IDispatchImpl` 0xFFFF 값을 가진 개체 `wMajor` 과 0xFFFF 값으로 `wMinor`, `IDispatchImpl` 클래스 레지스트리 대신.dll 파일에서 형식 라이브러리를 검색 합니다.  
  
 `IDispatchImpl`형식의 정적 멤버를 포함 `CComTypeInfoHolder` 는 이중 인터페이스의 형식 정보를 관리 합니다.  같은 이중 구현 하는 여러 개체의 경우 인터페이스를 하나의 인스턴스만 `CComTypeInfoHolder` 사용 됩니다.  
  
## 상속 계층 구조  
 `T`  
  
 `IDispatchImpl`  
  
## 요구 사항  
 **헤더:** atlcom.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)