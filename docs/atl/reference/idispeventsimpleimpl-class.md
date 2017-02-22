---
title: "IDispEventSimpleImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventSimpleImpl"
  - "ATL::IDispEventSimpleImpl"
  - "ATL.IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class"
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# IDispEventSimpleImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 구현을 제공 된 `IDispatch` 없는 형식 라이브러리에서 형식 정보를 가져오는 방법.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid  
>  
class ATL_NO_VTABLE IDispEventSimpleImpl :  
public _IDispEventLocator<nID, pdiid>  
```  
  
#### 매개 변수  
 `nID`  
 원본 개체의 고유 식별자입니다.  때 `IDispEventSimpleImpl` 기본 클래스는 합성 컨트롤의 경우이 매개 변수를 원하는 포함 된 컨트롤의 리소스 ID를 사용 합니다.  다른 경우에 임의의 양의 정수를 사용 합니다.  
  
 `T`  
 사용자 클래스에서 파생 된 `IDispEventSimpleImpl`.  
  
 `pdiid`  
 이 클래스에서 구현 된 이벤트 인터페이스의 IID에 대 한 포인터입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IDispEventSimpleImpl::Advise](../Topic/IDispEventSimpleImpl::Advise.md)|기본 이벤트 소스에 연결 합니다.|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|이벤트 소스에 연결 합니다.|  
|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|이벤트 소스와의 연결이 끊어집니다.|  
|[IDispEventSimpleImpl::GetIDsOfNames](../Topic/IDispEventSimpleImpl::GetIDsOfNames.md)|반환  **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](../Topic/IDispEventSimpleImpl::GetTypeInfo.md)|반환  **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](../Topic/IDispEventSimpleImpl::GetTypeInfoCount.md)|반환  **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](../Topic/IDispEventSimpleImpl::Invoke.md)|호출 된 이벤트 처리기는 이벤트 싱크 맵을 나열.|  
|[IDispEventSimpleImpl::Unadvise](../Topic/IDispEventSimpleImpl::Unadvise.md)|기본 이벤트 원본과 연결이 끊어집니다.|  
  
## 설명  
 `IDispEventSimpleImpl`해당 인터페이스의 모든 메서드\/이벤트에 대 한 구현 코드를 제공할 않아도 이벤트 인터페이스를 구현 하는 방법을 제공 합니다.  `IDispEventSimpleImpl`구현은 제공 된 `IDispatch` 메서드.  처리 하려는 이벤트에 대 한 구현을 제공 해야 합니다.  
  
 `IDispEventSimpleImpl`함께 작동 하는  [이벤트 싱크 맵](../Topic/BEGIN_SINK_MAP.md) 을 클래스 경로 이벤트를 해당 처리기 함수에.  이 클래스를 사용.  
  
-   추가 된  [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md) 이벤트 싱크 맵 처리 하려는 각 개체의 각 이벤트에 대 한 매크로.  
  
-   에 대 한 포인터를 전달 하 여 각 이벤트에 대 한 형식 정보를 제공 된  [\_ATL\_FUNC\_INFO](../../atl/reference/atl-func-info-structure.md) 각 항목에 대 한 매개 변수로 구조.  X86 플랫폼에는 `_ATL_FUNC_INFO.cc` 값은 CC\_CDECL 콜백 함수를 \_\_stdcall 메서드를 호출 합니다.  
  
-   호출  [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) 원본 개체에서 기본 클래스와 연결 합니다.  
  
-   호출  [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) 연결을 끊습니다.  
  
 파생 해야 `IDispEventSimpleImpl` \(고유 값을 사용 하 여 `nID`\) 이벤트를 처리 해야 하는 각 개체에 대 한.  여 바이 다른 원본 개체에 대해 다음 내용의 원본 개체에 대 한 기본 클래스를 다시 사용할 수 있지만 단일 개체에서 한 번에 처리할 수 있습니다 원본 개체의 최대 수에 따라 제한 됩니다 `IDispEventSimpleImpl` 기본 클래스입니다.  
  
 **IDispEventSimplImpl** 동일한 기능을 제공  [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 얻지 못하는 점을 제외 하 고.  마법사를 기반으로 빌드된 코드 생성 `IDispEventImpl`, 하지만 사용할 수 있습니다 `IDispEventSimpleImpl` 코드를 직접 추가 하 여.  사용 `IDispEventSimpleImpl` 때 이벤트 인터페이스를 설명 하는 형식 라이브러리가 없거나 형식 라이브러리를 사용 하 여 관련 된 오버 헤드를 방지 합니다.  
  
> [!NOTE]
>  `IDispEventImpl`및 `IDispEventSimpleImpl` 의 구현을 제공  **IUnknown::QueryInterface** 각 사용 `IDispEventImpl` 또는 `IDispEventSimpleImpl` 기본 클래스 기본 COM 개체에서 여전히 클래스 멤버에 직접 액세스를 허용 하면서 별도 COM id로 역할을 합니다.  
  
 CE ATL 구현만 이벤트 싱크를 지 원하는 ActiveX의 HRESULT 형식의 값을 반환 하거나 이벤트 처리기 메서드에서 무효가. 다른 모든 반환 값은 지원 되지 않습니다 및 해당 동작이 정의 되지 않습니다.  
  
 자세한 내용은  [IDispEventImpl 지원](../../atl/supporting-idispeventimpl.md).  
  
## 상속 계층 구조  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl Class](../../atl/reference/idispeventimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)