---
title: "CWindowImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWindowImpl"
  - "ATL.CWindowImpl"
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowImpl class"
  - "subclassing windows, ATL"
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CWindowImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

창을 만들거나 서브클래싱 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class TBase= CWindow,  
class TWinTraits= CControlWinTraits   
>  
class ATL_NO_VTABLE CWindowImpl :  
public CWindowImplBaseT< TBase, TWinTraits>  
```  
  
#### 매개 변수  
 `T`  
 새 클래스는 `CWindowImpl`에서 파생됩니다.  
  
 *TBase*  
 클래스의 기본 클래스입니다.  기본적으로, 기본 클래스는 [CWindow](../../atl/reference/cwindow-class.md)입니다.  
  
 `TWinTraits`  
 A [특성 클래스](../../atl/understanding-window-traits.md) 는 창 스타일을 정의합니다.  기본값은 `CControlWinTraits`입니다.  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CWindowImpl::Create](../Topic/CWindowImpl::Create.md)|창을 만듭니다.|  
  
### CWindowImplBaseT 메서드  
  
|||  
|-|-|  
|[DefWindowProc](../Topic/CWindowImpl::DefWindowProc.md)|기본 메시지 처리를 제공합니다.|  
|[GetCurrentThread](../Topic/CWindowImpl::GetCurrentMessage.md)|현재 메시지를 반환합니다.|  
|[GetWindowProc](../Topic/CWindowImpl::GetWindowProc.md)|현재 창 프로시저를 반환합니다.|  
|[OnFinalMessage](../Topic/CWindowImpl::OnFinalMessage.md)|마지막 메시지를 받은 후 호출 합니다 \(일반적으로 `WM_NCDESTROY`\).|  
|[SubclassWindow](../Topic/CWindowImpl::SubclassWindow.md)|창 서브클래스|  
|[UnsubclassWindow](../Topic/CWindowImpl::UnsubclassWindow.md)|이전에 서브클래싱된 창을 복원합니다.|  
  
### 정적 메서드  
  
|||  
|-|-|  
|[GetWndClassInfo](../Topic/CWindowImpl::GetWndClassInfo.md)|창 클래스 정보를 관리하는 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)의 정적 인스턴스를 반환합니다.|  
|[WindowProc](../Topic/CWindowImpl::WindowProc.md)|창으로 보내는 메시지를 처리 합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_pfnSuperWindowProc](../Topic/CWindowImpl::m_pfnSuperWindowProc.md)|창 클래스의 원본 창 프로시저를 가리킵니다.|  
  
## 설명  
 `CWindowImpl` 를 사용하여 기존 창 창 또는 하위 클래스를 만들 수 있습니다. `CWindowImpl` 창 프로시저는 해당 처리기에 메시지를 보낼 메시지 맵을 사용 합니다.  
  
 `CWindowImpl::Create` 는 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)에 관리되는 창 클래스 정보에 기반한 창을 만듭니다.  `CWindowImpl` 는 [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md) 매크로를 포함합니다. 이것은 `CWndClassInfo` 가 새 창 클래스를 등록한다는 의미입니다.  기존 창 클래스를 슈퍼클래스로 원한다면,  `CWindowImpl`  에서 클래스를 파생하고 [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md) 매크로를 포함시킵니다.  이 경우, `CWndClassInfo` 는 기존 클래스를 기반으로 하는 창 클래스 등록하지만 `CWindowImpl::WindowProc`을 사용합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/CPP/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  `CWndClassInfo` 는 한 윈도우 클래스의 정보를 관리하기 때문에, `CWindowImpl` 의 인스턴스를 통해 만들어진 각 창은 같은 창 클래스를 기반으로 합니다.  
  
 `CWindowImpl` 은 또한 창 서브클래싱도 지원합니다.  `SubclassWindow` 메서드는 기존 창을 `CWindowImpl` 개체에 붙이고 `CWindowImpl::WindowProc`에 윈도우 프로시저를 변경합니다.  `CWindowImpl` 의 각 인스턴스는 다른 창을 서브 클래스 할 수 있습니다.  
  
> [!NOTE]
>  주어진 `CWindowImpl` 개체에 대해, **만들기** 또는 `SubclassWindow` 중에서 하나를 호출합니다.  두 메서드 모두 동일한 개체에 호출 하지 마십시오.  
  
 `CWindowImpl` 이외에, ATL은[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 를 다른 개체에 포함된 창을 만들기 위해 제공합니다.  
  
 기본 클래스 소멸자는 \(~**CWindowImplRoot**\) 개체가 소멸 되기 전에 창에서 사라집니다.  
  
 `CWindowImpl` 은 **CWindowImplBaseT**에서 파생됩니다. 이것은 **CWindowImplRoot**에서 파생되었고, 이것은 또 **TBase** 및 [CMessageMap](../../atl/reference/cmessagemap-class.md)에서 파생됩니다.  
  
|추가 정보|참조|  
|-----------|--------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|ATL에서 창 사용하기|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
  
## 상속 계층 구조  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)