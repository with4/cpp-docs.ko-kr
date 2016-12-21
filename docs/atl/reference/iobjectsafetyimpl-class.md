---
title: "IObjectSafetyImpl Class | Microsoft Docs"
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
  - "IObjectSafetyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[ATL], safe"
  - "IObjectSafety, ATL 구현"
  - "IObjectSafetyImpl class"
  - "safe for scripting and initialization (controls)"
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IObjectSafetyImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 기본 구현을 제공 된 `IObjectSafety` 인터페이스를 검색 하 고 개체의 보안 수준 설정 하는 클라이언트를 허용 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template <class   
      T  
      , DWORD   
      dwSupportedSafety  
      >  
class IObjectSafetyImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 컨트롤에 대해 지원 되는 보안 옵션을 지정합니다.  다음 값 중 하나일 수 있습니다.  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_CALLER** 로 식별 되는 인터페이스는  [SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md) 매개 변수가 `riid` 덉 이루어져야 합니다.  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_DATA** 로 식별 되는 인터페이스는 `SetInterfaceSafetyOptions` 매개 변수가 `riid` 초기화 하는 동안 신뢰할 수 없는 데이터에 대 한 안전 이루어져야 합니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::GetInterfaceSafetyOptions.md)|보안 개체에 대 한 현재 설정 옵션 뿐만 아니라 개체에서 지 원하는 보안 옵션을 검색 합니다.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md)|개체 초기화 또는 스크립트에 대 한 안전 하 게 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[IObjectSafetyImpl::m\_dwCurrentSafety](../Topic/IObjectSafetyImpl::m_dwCurrentSafety.md)|개체의 현재 보안 수준을 저장합니다.|  
  
## 설명  
 클래스 `IObjectSafetyImpl` 의 기본 구현을 제공 합니다. `IObjectSafety`.  `IObjectSafety` 인터페이스를 검색 하 고 개체의 보안 수준 설정 하는 클라이언트 수 있습니다.  웹 브라우저를 호출할 수 있습니다 예를 들어,  **IObjectSafety::SetInterfaceSafetyOptions** 컨트롤 초기화에 안전 또는 스크립트 사용에 안전 합니다.  
  
 사용 참고는  [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md) 매크로 사용 하는  **CATID\_SafeForScripting** 및  **CATID\_SafeForInitializing** 구성 요소 범주 구성 요소는 안전입니다 지정 하는 다른 방법을 제공 합니다.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [IObjectSafety Interface](https://msdn.microsoft.com/en-us/library/aa768224.aspx)   
 [Class Overview](../../atl/atl-class-overview.md)