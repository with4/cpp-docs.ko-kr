---
title: "IViewObjectExImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IViewObjectExImpl<T>"
  - "ATL.IViewObjectExImpl"
  - "ATL::IViewObjectExImpl"
  - "ATL.IViewObjectExImpl<T>"
  - "IViewObjectExImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], drawing"
  - "advise sinks"
  - "IViewObjectEx ATL implementation"
  - "IViewObjectExImpl class"
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IViewObjectExImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 구현 합니다.  **IUnknown** 의 기본 구현을 제공 하 고 있는  [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763),  [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), 및  [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) 인터페이스.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IViewObjectExImpl :  
public IViewObjectEx  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IViewObjectExImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IViewObjectExImpl::Draw](../Topic/IViewObjectExImpl::Draw.md)|제어 장치 컨텍스트에 표시를 그립니다.|  
|[IViewObjectExImpl::Freeze](../Topic/IViewObjectExImpl::Freeze.md)|컨트롤의 그리기 표현까지 변하지를 동결 된 `Unfreeze`.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](../Topic/IViewObjectExImpl::GetAdvise.md)|있을 경우 기존 advise 싱크 연결 컨트롤을 검색 합니다.|  
|[IViewObjectExImpl::GetColorSet](../Topic/IViewObjectExImpl::GetColorSet.md)|컨트롤에서 드로잉에 사용 되는 논리 색상표를 반환 합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](../Topic/IViewObjectExImpl::GetExtent.md)|컨트롤의 표시 크기를 HIMETRIC 단위 \(0.01 밀리미터 단위\) 컨트롤 클래스 데이터 멤버에서 검색  [CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md).|  
|[IViewObjectExImpl::GetNaturalExtent](../Topic/IViewObjectExImpl::GetNaturalExtent.md)|크기 조정 힌트를 조정할 때 사용 하는 개체에 대 한 컨테이너를 제공 합니다.|  
|[IViewObjectExImpl::GetRect](../Topic/IViewObjectExImpl::GetRect.md)|요청한 그리기 모양을 설명 하는 사각형을 반환 합니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](../Topic/IViewObjectExImpl::GetViewStatus.md)|드로잉 요소에 지원 되는 개체의 불투명도 대 한 정보를 반환 합니다.|  
|[IViewObjectExImpl::QueryHitPoint](../Topic/IViewObjectExImpl::QueryHitPoint.md)|지정 된 위치에서 지정 된 사각형 및 반환 경우 검사는  [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) 값에 `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](../Topic/IViewObjectExImpl::QueryHitRect.md)|컨트롤의 표시 영역에 겹치는 모든 위치에서 위치를 지정 된 사각형 및 반환 여부 확인은  **HITRESULT**  값에 `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](../Topic/IViewObjectExImpl::SetAdvise.md)|싱크 보기 컨트롤의 변경 내용에 대 한 알림을 받을 수 있도록 컨트롤와 advise 싱크 간의 연결을 설정 합니다.|  
|[IViewObjectExImpl::Unfreeze](../Topic/IViewObjectExImpl::Unfreeze.md)|컨트롤의 그리기 표현을 unfreezes.  ATL 구현을 반환  **E\_NOTIMPL**.|  
  
## 설명  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763),  [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), 및  [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) 인터페이스 자체를 직접 표시 하려면 만들기 및 컨테이너 컨트롤 표시에서 변경 내용을 알릴 advise 싱크를 관리 하는 컨트롤을 사용 합니다.  **IViewObjectEx** 인터페이스 깜빡임 없는 드로잉, 투명 한 사각형이 아닌 컨트롤, 적중 테스트 \(예를 들어, 얼마나 가까운 마우스 클릭 컨트롤에서 고려해 야 할 이어야 함\) 등의 확장된 컨트롤 기능에 대 한 지원을 제공 합니다.  클래스 `IViewObjectExImpl` 는 이러한 인터페이스의 기본 구현을 제공 하 고 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
## 상속 계층 구조  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [자습서](../../atl/active-template-library-atl-tutorial.md)   
 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)   
 [Class Overview](../../atl/atl-class-overview.md)