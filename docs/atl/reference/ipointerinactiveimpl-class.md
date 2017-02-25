---
title: "IPointerInactiveImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPointerInactiveImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inactive objects"
  - "IPointerInactive ATL implementation"
  - "IPointerInactiveImpl class"
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPointerInactiveImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** ,  [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) 인터페이스 메서드.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IPointerInactiveImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPointerInactiveImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IPointerInactiveImpl::GetActivationPolicy](../Topic/IPointerInactiveImpl::GetActivationPolicy.md)|현재 활성화 정책 개체를 검색합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](../Topic/IPointerInactiveImpl::OnInactiveMouseMove.md)|마우스 포인터, 개체 이동은 마우스 이벤트를 발생 수를 알립니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](../Topic/IPointerInactiveImpl::OnInactiveSetCursor.md)|비활성 개체에 마우스 포인터를 설정합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
  
## 설명  
 비활성 개체 로드 또는 실행 하기만 하면 하나입니다.  현재 개체와는 달리, 비활성 개체 Windows 마우스 및 키보드 메시지를 받을 수 없습니다.  따라서, 비활성 개체 리소스를 적게 사용 하 고 일반적으로 더 효율적입니다.  
  
 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) 인터페이스 개체 최소 수준의 비활성 하면서 마우스 상호 작용을 지 원하는 데 있습니다.  컨트롤의 경우이 기능이 특히 유용합니다.  
  
 클래스 `IPointerInactiveImpl` 구현 된 `IPointerInactive` 메서드를 반환 하면  **E\_NOTIMPL**.  그러나 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)