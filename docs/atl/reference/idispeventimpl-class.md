---
title: "IDispEventImpl Class | Microsoft Docs"
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
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class"
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispEventImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 구현을 제공 된 `IDispatch` 방법.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid= &IID_NULL,  
const GUID* plibid= &GUID_NULL,  
WORD wMajor= 0,  
WORD wMinor= 0,  
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE IDispEventImpl :  
public IDispEventSimpleImpl<nID, T, pdiid>  
```  
  
#### 매개 변수  
 `nID`  
 원본 개체의 고유 식별자입니다.  때 `IDispEventImpl` 기본 클래스는 합성 컨트롤의 경우이 매개 변수를 원하는 포함 된 컨트롤의 리소스 ID를 사용 합니다.  다른 경우에 임의의 양의 정수를 사용 합니다.  
  
 `T`  
 사용자 클래스에서 파생 된 `IDispEventImpl`.  
  
 `pdiid`  
 이 클래스에서 구현 된 이벤트 인터페이스의 IID에 대 한 포인터입니다.  이 인터페이스에서 표시 하는 형식 라이브러리 정의 해야 `plibid`, `wMajor`, 및 `wMinor`.  
  
 `plibid`  
 디스패치 인터페이스를 정의 하는 형식 라이브러리에 대 한 포인터에서를 가리키는 `pdiid`.  경우  **& GUID\_NULL**, 소싱 이벤트 개체에서 형식 라이브러리를 로드 됩니다.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다.  기본값은 0입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다.  기본값은 0입니다.  
  
 `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`.  클래스 형식의 기본값은 `CComTypeInfoHolder`. 그러나 다른 형식의 클래스를 제공 하 여이 템플릿 매개 변수를 무시할 수 있습니다 `CComTypeInfoHolder`.  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[IDispEventImpl::\_tihclass](../../atl/reference/idispeventimpl-class.md)|형식 정보를 관리 하는 데 사용 되는 클래스입니다.  기본적으로 `CComTypeInfoHolder`입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[IDispEventImpl::IDispEventImpl](../Topic/IDispEventImpl::IDispEventImpl.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IDispEventImpl::GetFuncInfoFromId](../Topic/IDispEventImpl::GetFuncInfoFromId.md)|지정 된 디스패치 식별자 함수 인덱스를 찾습니다.|  
|[IDispEventImpl::GetIDsOfNames](../Topic/IDispEventImpl::GetIDsOfNames.md)|단일 구성원 및 선택적 인수 이름의 집합 해당 정수 Dispid 집합에 매핑합니다.|  
|[IDispEventImpl::GetTypeInfo](../Topic/IDispEventImpl::GetTypeInfo.md)|개체의 형식 정보를 검색합니다.|  
|[IDispEventImpl::GetTypeInfoCount](../Topic/IDispEventImpl::GetTypeInfoCount.md)|형식 정보 인터페이스의 수를 검색합니다.|  
|[IDispEventImpl::GetUserDefinedType](../Topic/IDispEventImpl::GetUserDefinedType.md)|사용자 정의 형식의 기본 형식을 검색합니다.|  
  
## 설명  
 `IDispEventImpl`해당 인터페이스의 모든 메서드\/이벤트에 대 한 구현 코드를 제공할 않아도 이벤트 인터페이스를 구현 하는 방법을 제공 합니다.  `IDispEventImpl`구현은 제공 된 `IDispatch` 메서드.  처리 하려는 이벤트에 대 한 구현을 제공 해야 합니다.  
  
 `IDispEventImpl`함께 작동 하는  [이벤트 싱크 맵](../Topic/BEGIN_SINK_MAP.md) 을 클래스 경로 이벤트를 해당 처리기 함수에.  이 클래스를 사용.  
  
 추가 된  [SINK\_ENTRY](../Topic/SINK_ENTRY.md) 또는  [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) 이벤트 싱크 맵 처리 하려는 각 개체의 각 이벤트에 대 한 매크로.  사용 하는 경우 `IDispEventImpl` 합성 컨트롤의 기본 클래스로 호출할 수 있는  [AtlAdviseSinkMap](../Topic/AtlAdviseSinkMap.md) 설정 하 고 맵 모든 엔트리를 이벤트 싱크를 이벤트 소스에 연결을 해제 합니다.  다른 경우에서 또는 큰 컨트롤에 대 한 호출  [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) 원본 개체에서 기본 클래스와 연결 합니다.  호출  [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) 연결을 끊습니다.  
  
 파생 해야 `IDispEventImpl` \(고유 값을 사용 하 여 `nID`\) 이벤트를 처리 해야 하는 각 개체에 대 한.  여 바이 다른 원본 개체에 대해 다음 내용의 원본 개체에 대 한 기본 클래스를 다시 사용할 수 있지만 단일 개체에서 한 번에 처리할 수 있습니다 원본 개체의 최대 수에 따라 제한 됩니다 `IDispEventImpl` 기본 클래스입니다.  
  
 `IDispEventImpl`동일한 기능을 제공  [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), 제공에 대 한 포인터를 사용 하지 않고 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 가져옵니다 제외 하 고는  [\_ATL\_FUNC\_INFO](../../atl/reference/atl-func-info-structure.md) 구조.  사용 `IDispEventSimpleImpl` 때 하면 이벤트 인터페이스를 설명 하는 형식 라이브러리가 없거나 형식 라이브러리를 사용 하 여 관련 된 오버 헤드를 방지 하려면.  
  
> [!NOTE]
>  `IDispEventImpl`및 `IDispEventSimpleImpl` 의 구현을 제공  **IUnknown::QueryInterface** 각 사용 `IDispEventImpl` 및 `IDispEventSimpleImpl` 기본 클래스 기본 COM 개체에서 여전히 클래스 멤버에 직접 액세스를 허용 하면서 별도 COM id로 역할을 합니다.  
  
 CE ATL 구현만 이벤트 싱크를 지 원하는 ActiveX의 HRESULT 형식의 값을 반환 하거나 이벤트 처리기 메서드에서 무효가. 다른 모든 반환 값은 지원 되지 않습니다 및 해당 동작이 정의 되지 않습니다.  
  
 자세한 내용은  [IDispEventImpl 지원](../../atl/supporting-idispeventimpl.md).  
  
## 상속 계층 구조  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY](../Topic/SINK_ENTRY.md)   
 [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)