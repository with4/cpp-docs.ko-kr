---
title: "IPerPropertyBrowsingImpl Class | Microsoft Docs"
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
  - "ATL.IPerPropertyBrowsingImpl"
  - "IPerPropertyBrowsing"
  - "ATL::IPerPropertyBrowsingImpl"
  - "ATL::IPerPropertyBrowsingImpl<T>"
  - "IPerPropertyBrowsingImpl"
  - "ATL.IPerPropertyBrowsingImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPerPropertyBrowsing, ATL 구현"
  - "IPerPropertyBrowsingImpl class"
  - "속성 페이지, accessing information"
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPerPropertyBrowsingImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 및 클라이언트 개체의 속성 페이지에 있는 정보에 액세스할 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :  
public IPerPropertyBrowsing  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPerPropertyBrowsingImpl`.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](../Topic/IPerPropertyBrowsingImpl::GetDisplayString.md)|지정 된 속성을 설명 하는 문자열을 검색 합니다.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](../Topic/IPerPropertyBrowsingImpl::GetPredefinedStrings.md)|지정 된 속성을 사용할 수 있는 값에 해당 하는 문자열의 배열을 검색 합니다.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](../Topic/IPerPropertyBrowsingImpl::GetPredefinedValue.md)|검색은  **변형** 는 지정 된 DISPID가 식별 되는 속성의 값이 들어.  DISPID는 검색 문자열 이름을 가진 연결 된 `GetPredefinedStrings`.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](../Topic/IPerPropertyBrowsingImpl::MapPropertyToPage.md)|지정 된 속성과 관련 된 속성 페이지의 CLSID를 검색 합니다.|  
  
## 설명  
 [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) 인터페이스 클라이언트 개체의 속성 페이지에 있는 정보에 액세스할 수 있습니다.  클래스 `IPerPropertyBrowsingImpl` 는이 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
> [!NOTE]
>  컨테이너 응용 프로그램으로 Microsoft Access를 사용 하는 경우 클래스에서 파생 되어야 `IPerPropertyBrowsingImpl`.  그렇지 않으면 액세스 컨트롤을 로드할 수 없습니다.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [IPropertyPageImpl Class](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)