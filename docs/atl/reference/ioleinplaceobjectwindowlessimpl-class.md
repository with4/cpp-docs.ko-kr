---
title: "IOleInPlaceObjectWindowlessImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IOleInPlaceObjectWindowlessImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activation [C++], ATL"
  - "ActiveX 컨트롤[C++], communication between container and control"
  - "컨트롤[ATL], windowless"
  - "deactivating ATL"
  - "IOleInPlaceObjectWindowless, ATL 구현"
  - "IOleInPlaceObjectWindowlessImpl class"
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IOleInPlaceObjectWindowlessImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 구현  **IUnknown** 및 끌어서 놓기 작업에 참여 한 창 메시지를 받을 수 없는 컨트롤을 사용할 수 있는 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      >  
class IOleInPlaceObjectWindowlessImpl  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IOleInPlaceObjectWindowlessImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](../Topic/IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp.md)|상황에 맞는 도움말이 있습니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](../Topic/IOleInPlaceObjectWindowlessImpl::GetDropTarget.md)|공급 장치는 `IDropTarget` 끌어서 놓기를 지원 현재 위치에서 활성화, 창 없는 개체에 대 한 인터페이스.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](../Topic/IOleInPlaceObjectWindowlessImpl::GetWindow.md)|창 핸들을 가져옵니다.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate.md)|내부 activex 컨트롤이 비활성화 됩니다.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](../Topic/IOleInPlaceObjectWindowlessImpl::OnWindowMessage.md)|컨테이너를 현재 위치에서 활성화 되는 창 없는 컨트롤에 메시지를 디스패치합니다.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](../Topic/IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo.md)|이전에 비활성화 된 컨트롤이 다시 활성화 됩니다.  ATL 구현을 반환  **E\_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](../Topic/IOleInPlaceObjectWindowlessImpl::SetObjectRects.md)|내부 컨트롤의 일부 표시 되는지 나타냅니다.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](../Topic/IOleInPlaceObjectWindowlessImpl::UIDeactivate.md)|비활성화 하 고 현재 위치에서 활성화를 지 원하는 사용자 인터페이스를 제거 합니다.|  
  
## 설명  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) 인터페이스 관리를 다시 활성화 및 비활성화 하는 장소에서 제어 하 고 컨트롤의 양을 표시할지를 결정 합니다.  [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) 인터페이스 창 없는 컨트롤이 끌어서 놓기 작업에 참여 한 창 메시지를 받을 수 있습니다.  클래스 `IOleInPlaceObjectWindowlessImpl` 의 기본 구현을 제공 합니다. `IOleInPlaceObject` 및 `IOleInPlaceObjectWindowless` 및 구현  **IUnknown** 덤프에 정보를 전송 하 여 장치에서 디버그 빌드.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)